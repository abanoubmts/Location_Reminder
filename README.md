# Location_Reminder
# Location_Reminder
# Location Reminder

A Todo list app with location reminders that remind the user to do something when he reaches a specific location. The app will require the user to create an account and login to set and access reminders.

## Getting Started

1. Clone the project to your local machine.
2. Open the project using Android Studio.

### Dependencies

```
1. A created project on Firebase console.
2. A create a project on Google console.
```

### Installation

Step by step explanation of how to get a dev environment running.

```
1. To enable Firebase Authentication:
        a. Go to the authentication tab at the Firebase console and enable Email/Password and Google Sign-in methods.
        b. download `google-services.json` and add it to the app.
2. To enable Google Maps:
    a. Go to APIs & Services at the Google console.
    b. Select your project and go to APIs & Credentials.
    c. Create a new api key and restrict it for android apps.
    d. Add your package name and SHA-1 signing-certificate fingerprint.
    c. Enable Maps SDK for Android from API restrictions and Save.
    d. Copy the api key to the `google_maps_api.xml`
3. Run the app on your mobile phone or emulator with Google Play Services in it.
```

## Testing

Right click on the `test` or `androidTest` packages and select Run Tests

### Break Down Tests

Explain what each test does and why

```
1.androidTest
        //TODO: Students explain their testing here.
        Android  test - which runs on the Android runtime
		
the implementation steps :- 

to implement the below test cases for RemindersDaoTest
1) Prepare the before & after for Using an in-memory database so that the information stored here disappears when the
 process is killed
2) getReminders
3) insertReminder_GetById
4) getReminderByIdNotFound
5) deleteReminders

to implement the below test cases for RemindersLocalRepositoryTest

1) Prepare the before & after for Using an in-memory database so that the information stored here disappears when the
 process is killed
2) addReminder_getReminderById
3) deleteReminders_EmptyList
4) getReminderById_ReturnError

to implement the below test cases for ReminderListFragmentTest

1) Prepare the before & after for Using an in-memory database so that the information stored here disappears when the
 process is killed
2) addReminder_getReminderById
3) deleteReminders_EmptyList
4) getReminderById_ReturnError

to implement the below test cases for RemindersActivityTest and apply Test Framework
{Use Espresso and Mockito to test the app UI (each screen of the app) and Fragments Navigation}

1) before >> registerIdlingResource
Idling resources tell Espresso that the app is idle or busy
2) after >> unregisterIdlingResource
Unregister your Idling Resource so it can be garbage collected and does not leak any memory.
3) saveReminderScreen_showSnackBarTitleError
4) saveReminderScreen_showSnackBarLocationError
5) saveReminderScreen_showToastMessage


        
2. test
        //TODO: Students explain their testing here.
        local unit test - which runs on the JVM 

the implementation steps 

apply the location reminder test 

1) Create a fake data source to act as a double to the real data source
2) getReminders
3) saveReminder
4) getReminder by ID 
5) deleteAllReminders


implement RemindersListViewModelTest  

1) create new class MainCoroutine & live data function 
maincoroutine conatins two main functions (start / finish) by using dispatcher 
2) getReminders
3) saveReminder
4) getReminder by ID 
5) deleteAllReminders


implement testing to the SaveReminderView and its live data objects


1) check_loading
fakeDataSource = FakeDataSource()
        saveReminderViewModel 
        mainCoroutineRule.pauseDispatcher()
        validateAndSaveReminder(firstReminder)
        Assert.assertThat

2) check error if title is null as a sample 


        
extra info :- 
        
@Test – This annotation is a replacement of org.junit.TestCase which indicates that the 
public void method to which it is attached can be executed as a Test Case.

testFragmentsNavigation   in class ReminderList fragment Test 
testNoDataDisplayed in class ReminderList fragment Test 



STEPS :  
1) Create the ValidationUtilTest class   (Reminder DAO TEST )and write the 
unit test case for testInsertRetrieveData  function.
2) To check THE POINT NO 1 , used Junit assertEquals OR { MatcherAssert.assertThat(loadedDataList.size, `is`(1))} function 
to check the result and expected it
3) Write test for view models (before / after)
  3.1  In the @Before  annotation is used if you want to execute some statements such as 
preconditions before each test case.
so we have configured the viewModel and the repository (databaseSource) by initDb / registerIdlingResource / setup  Function .

  3.2  In the @After annotation can be used if you want to execute some statements after each 
so we execute close DB  / unregisterIdlingResource  / cleanUp 


4) CREATE Fake and Real Data Sources 


5) Write tests for Repository
Repository fetches data from the API, and when wa want to write a unit testing 
we have to fake this data {refer to point no 4}, so, we have to 
build a fake data source instead of the API.
Using Koin in Dependency Injection, we 
can inject the repository (dataSource) 
and then get it.
By startKoin{ } and pass all the required 
module e.g >>  modules(listOf(myModule)) that defined << RemindersListViewModel >>           

```

## Project Instructions
    1. Create a Login screen to ask users to login using an email address or a Google account.  Upon successful login, navigate the user to the Reminders screen.   If there is no account, the app should navigate to a Register screen.
    2. Create a Register screen to allow a user to register using an email address or a Google account.
    3. Create a screen that displays the reminders retrieved from local storage. If there are no reminders, display a   "No Data"  indicator.  If there are any errors, display an error message.
    4. Create a screen that shows a map with the user's current location and asks the user to select a point of interest to create a reminder.
    5. Create a screen to add a reminder when a user reaches the selected location.  Each reminder should include
        a. title
        b. description
        c. selected location
    6. Reminder data should be saved to local storage.
    7. For each reminder, create a geofencing request in the background that fires up a notification when the user enters the geofencing area.
    8. Provide testing for the ViewModels, Coroutines and LiveData objects.
    9. Create a FakeDataSource to replace the Data Layer and test the app in isolation.
    10. Use Espresso and Mockito to test each screen of the app:
        a. Test DAO (Data Access Object) and Repository classes.
        b. Add testing for the error messages.
        c. Add End-To-End testing for the Fragments navigation.


## Student Deliverables:

1. APK file of the final project.
2. Git Repository with the code.

## Built With

* [Koin](https://github.com/InsertKoinIO/koin) - A pragmatic lightweight dependency injection framework for Kotlin.
* [FirebaseUI Authentication](https://github.com/firebase/FirebaseUI-Android/blob/master/auth/README.md) - FirebaseUI provides a drop-in auth solution that handles the UI flows for signing
* [JobIntentService](https://developer.android.com/reference/androidx/core/app/JobIntentService) - Run background service from the background application, Compatible with >= Android O.

## License
