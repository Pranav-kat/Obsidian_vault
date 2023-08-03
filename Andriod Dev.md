---
share: true
---

* **Fetching the text field data:**
* Retrieving the data in the console: 
  EditText editTextTextPersonName =  findViewById(R.id.editTextTextPersonName);  
 Log.i("info", editTextTextPersonName.getText().toString()); 
 + onClick attribute of the button must be passed the click event function. 

*Displaying the alert message (Toast):
 Toast.makeText(this, X.getText()+"You clicked Click Me",  Toast.LENGTH_LONG).show();
 - Toast.LENGTH_SHORT - indicates that the display time is short.

*Changing the image by clicking it and also setting the image:
  //in onCreate method 
 ImageView image = findViewById(R.id.imageView2);  //position
 image.setImageResource(R.drawable.pranav2);   //target
 
VideoView
   //in onCreate method 
  VideoView video = (VideoView) findViewById(R.id.videoView);  //source
 video.setVideoPath("android.resource://"+getPackageName()+ "/"+R.raw.cam);  //vid
 video.start(); // without any controls

 //with controls: 
 MediaController media = new MediaController(this);  
 media.setAnchorView(video);  
 video.setMediaController(media);  
 video.start();
 
Audio Controls:
  first set the audio in the resources
  import android.media.MediaPlayer;
  //in onCreate method 
  MediaPlayer mplayer = MediaPlayer.create(this, R.raw.laugh);
  mplayer.start(); // without controls
  
  create two buttons: PLAY PAUSE
  create two onclick methods play and pause..
  define the mplayer outside the method.
  in play method:
  mplayer.start();
  
  in pause method: //STOP method 
  mplayer.pause(); //mplayer.stop(); 
  

*Currency Converter*
 EditText dollar = findViewById(R.id.editTextNumber);  
 Double ddollar = Double.parseDouble(dollar.getText().toString());  
 Double pound = ddollar*0.75;  
 Toast.makeText(this, pound.toString(), Toast.LENGTH_LONG).show();

**Layouts**
*horizontals in verticals*
<LinearLayout  
    android:id="@+id/linearLayout3"  
    android:layout_width="0dp"  
    android:layout_height="0dp"  
    android:layout_marginStart="8dp"  
    android:layout_marginTop="16dp"  
    android:layout_marginEnd="8dp"  
    android:layout_marginBottom="49dp"  
    android:orientation="vertical"  
    app:layout_constraintBottom_toTopOf="@+id/editTextTextPersonName"  
    app:layout_constraintEnd_toEndOf="parent"  
    app:layout_constraintHorizontal_bias="0.0"  
    app:layout_constraintStart_toStartOf="parent"  
    app:layout_constraintTop_toTopOf="parent">  
  
    <LinearLayout        android:id="@+id/linearLayout2"  
        android:layout_width="391dp"  
        android:layout_height="87dp"  
        android:orientation="horizontal">  
  
        <Button            android:id="@+id/button"  
            android:layout_width="172dp"  
            android:layout_height="wrap_content"  
            android:layout_marginStart="12dp"  
            android:layout_marginTop="12dp"  
            android:minHeight="48dp"  
            android:onClick="clickFunction"  
            android:text="@string/click_me"  
            tools:ignore="TouchTargetSizeCheck" />  
  
        <Button            android:id="@+id/button1"  
            android:layout_width="196dp"  
            android:layout_height="wrap_content"  
            android:layout_marginStart="12dp"  
            android:layout_marginTop="12dp"  
            android:minHeight="48dp"  
            android:onClick="clickFunction"  
            android:text="@string/click_me" />  
  
        <LinearLayout            android:layout_width="match_parent"  
            android:layout_height="match_parent"  
            android:orientation="vertical"></LinearLayout>  
    </LinearLayout>  
	
    <LinearLayout        android:id="@+id/linearLayout4"  
        android:layout_width="391dp"  
        android:layout_height="82dp"  
        android:orientation="horizontal">  
  
        <Button            android:id="@+id/button3"  
            android:layout_width="172dp"  
            android:layout_height="wrap_content"  
            android:layout_marginStart="12dp"  
            android:layout_marginTop="12dp"  
            android:minHeight="48dp"  
            android:onClick="clickFunction"  
            android:text="@string/click_me" />  
  
        <Button            android:id="@+id/button4"  
            android:layout_width="196dp"  
            android:layout_height="wrap_content"  
            android:layout_marginStart="12dp"  
            android:layout_marginTop="12dp"  
            android:minHeight="48dp"  
            android:onClick="clickFunction"  
            android:text="@string/click_me" />  
  
  
        <LinearLayout            android:layout_width="match_parent"  
            android:layout_height="match_parent"  
            android:orientation="vertical"></LinearLayout>  
    </LinearLayout></LinearLayout>


**Image animation**
*transparency*
    public void fade(View view){  
    ImageView image = findViewById(R.id.imageView2);  
    image.animate().alpha(0f).setDuration(2000);  //fade in fade out.. alpha controls the transparency
	
*Translation*
   image.animate().translationXBy(1000f).setDuration(2000); // slides the image to the corresponding axis (X,Y,Z); set duration is in microseconds. 
   
   image.setTranslationY(1000f); // instant translation without animation 
   
   initialize an image as outside the frame in the onCreate function; then with the help of other images, get back our OG image. 
  	     for instance: protected void onCreate(Bundle savedInstanceState) {  
   		 super.onCreate(savedInstanceState);  
   		 setContentView(R.layout.activity_main);  
   		 ImageView image = findViewById(R.id.imageView2);  
   		 image.setTranslationY(-1000f);  
		 }		 
		 
*Rotation*
 image.animate().rotation(180f).setDuration(2000); // in the given duration, the image will rotate X degrees.. hence the speed depends on the duration and the degree of rotation. 
 
*Shrinking and growing*
 image.animate().scaleX(0.5f).scaleY(0.5f).setDuration(2000);
	


