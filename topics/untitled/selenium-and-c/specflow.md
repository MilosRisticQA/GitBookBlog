# SpecFlow

Example:

### Feature file:

```yaml
@automated


@alternative_syntax
@WI8
Scenario: Cheapest 3 books should be listed on the home screen (table syntax)
	When I enter the shop
	Then the home screen should show the following books
		|Title															|
		|Bridging the Communication Gap			|
		|Inside Windows SharePoint Services	|
		|Domain Driven Design								|
```

### Step definitions:

```csharp
using System;
using TechTalk.SpecFlow;
using BookShop.AcceptanceTests.Drivers.Home;

namespace BookShop.AcceptanceTests.StepDefinitions
{
    [Binding]
    public class HomeSteps
    {
        private readonly HomeDriver _homeDriver;

        public HomeSteps(HomeDriver driver)
        {
            _homeDriver = driver ?? throw new ArgumentNullException(nameof(driver));
        }

        [When(@"I enter the shop")]
        public void WhenIEnterTheShop()
        {
            _homeDriver.Navigate();
        }

        [Then(@"the home screen should show the book '(.*)'")]
        public void ThenTheHomeScreenShouldShowTheBook(string expectedTitle)
        {
            _homeDriver.ShowsBook(expectedTitle);
        }

        [Then(@"the home screen should show the books (.*)")]
        public void ThenTheHomeScreenShouldShowTheBooks(string expectedTitleList)
        {
            _homeDriver.ShowsBooks(expectedTitleList);
        }

        [Then(@"the home screen should show the following books")]
        public void ThenTheHomeScreenShouldShowTheFollowingBooks(Table expectedBooks)
        {
            _homeDriver.ShowsBooks(expectedBooks);
         }

    }
}
```

