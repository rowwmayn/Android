# Jetpack Compose 
Compose is the current industry standard UI making tool for android. 
In Jetpack compose, everything is made up from composable functions. 
Each composable functions have a wrapper '@composable'.
Everytime the data changes, compose recomposes the composables.
'@preview' let's us preview the composable in real time.

### Remove the previous composables from the template projects
#### Create a new file inside the Kotlin+Java folder and rename it with the name you'll use for the name of the composable

`
@preview(showBackground = true)
@composable
fun LoginScreen() // Name of the file itself LoginScreen.kt
// Paste image into the drawable folder
Box (modifier = Modifier.fillMaxSize()
                        .background(color = Color.White)){

    Image(painter = painterResource(id=R.drawable.students),
    contentDescription = "Students")

    Text(
        text = "Skip",
        color = Color.White,
        fontSize = 16sp,
        fontWeight = FontWeight.Bold,
        modifier = Modifier.align(Alignment.TopEnnd)
                           .padding(top=48dp, end=24dp)
                           .clickable(onClick = {/*Pending*/})
    )


}

`





/////////////////////






# Activities and Activity Lifecycle
**Activities: ** Activities are basically the screens in the android app; but, let's just not assume these are not just screens rather units of the app. Activities can also be thought of as the entry-point of the app such as assume whenever an user opens an app from a link or something similar and the application jumps open then from that point the activity starts. Android development has changed quite a fair bit from the olden days. We usually had one activity per screen but currently we have fragments and bundles such as the sign in option where we can think like the profile sign in option might have different activities per action; so, for all these reasons it's better to think of activites as an unit not just screens but for small projects the screen method really do work.
Jetpack compose also kind of makes it like a single activity in the whole app.
In pure Jetpack Compose app the `MainActivity` is the starting point of our entire app!

### Activity Lifecycle

**0. Activity Created**
Initialises the variables. 
Set the actual viewer.
The user still doesn't see anything on the screen.
**1. onCreate()**
You can think of it like in a play where the curtains have drawn out and you can see the actors and sctresses but the play itself hasn't started yet. But you can see it that it has started. So basically the activity or the screen is visible.
**2. onStart()**
This is where the activity has actually has finally started. This state usually lasts very small time and in a normal process it usually jumps straight to the next phase.
**3. onResume()**
This is where the activity is interactable with the user. The user play has started users can now throw tomatoes or cheer as much as they want.
**4. onPause()**
When another activity came into the foreground for that the previous activity stops maybe temporarily but again it can go back to `onResume()` as it wishes. All background processes might still remain active for the time being. It still may be visible but it's still in the memory.
**5. onStop()**
This is where the activity stops if it's on pause for an extended amount of time. This where the background processes finally stop. It's no longer visible.
**6. onRestart()**
A special phase where after an activity has stopped, it can be restarted again but it'll move back to `onCreate()` then again start the activity. It'll again be initialised.
**7. onDestroy()**
Activity finally shuts down and every process is released back.


# MVVM

### Model, View, View Model

**Model:** Handles the data and business rules of the application.
Fetches and saves from local databases.
**View:** Shows the UI to the user. The screen, activity and Jetpack Compose elements.
Observes data changes and forwards user clicks to the ViewModel.
**ViewModel:** Acts as a secure bridge view and model. Prepares and manages data for the UI. 
Does not hold direct reference to the View, preventing memory leaks and crashes.