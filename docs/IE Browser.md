The Inferno (g)(10) Standardized API test kit provides a web user interface that currently does not support the use of Internet Explorer. _Microsoft Edge_, _Firefox_, _Safari_, or _Chrome_ are recommended for use by the tester that is executing the Inferno tests.

Inferno tests the **EHR Practitioner App** launch functionality by instructing the system under test to launch the Inferno application from within the EHR interface.  In cases where the system under test uses Internet Explorer as an embedded browser to launch these applications, Inferno will not render properly.  Since the ONC (g)(10) Standardized API Certification Criterion does not specify constraints on browsers used within the EHR to launch 3rd party applications, the following steps may be taken to test these systems.

## Step 1

On a system separate from the EHR being tested, launch Inferno from within Microsoft Edge, Firefox, Safari, or Chrome browser.  

![legacy_step1a](https://user-images.githubusercontent.com/412901/182948775-302e9d62-d487-47fc-bde7-96d3b3bd5174.png)

Start the **EHR Practitioner App** test.

![legacy_step1b](https://user-images.githubusercontent.com/412901/182948935-362bf175-2e24-4a27-a8d1-8d5652f35ab4.png)

Inferno will pause, indicating that it is waiting for the EHR to initiate a launch to Inferno.

![legacy_step1c](https://user-images.githubusercontent.com/412901/182949051-7a369573-8011-4ab0-9926-c4adf40b50d7.png)

## Step 2

Outside of the browser that is running the Inferno tests, open the EHR and navigate to where the Inferno application will be launched.  The inferno reference server site provides a simple interface to launch inferno -- the EHR will have a different interface than this.  Note that IE11 mode is enabled to demonstrate what this will look like for EHRs using Internet Explorer as an embedded browser to launch applications.

![legacy_step2a](https://user-images.githubusercontent.com/412901/182949416-13231507-00f0-47c1-a321-5b2fdf4e3645.png)

Launch the Inferno application.  You will be presented with a mostly blank screen.

![legacy_step2b](https://user-images.githubusercontent.com/412901/182949600-d420e758-f82b-441c-b7ce-b214aabae6f0.png)

## Step 3

Returning to the original browser that began the tests, the tests will now proceed to the next step, indicating that Inferno will redirect the browser back to the system under test.

![legacy_step3a](https://user-images.githubusercontent.com/412901/182949725-5327dc1e-900a-40fc-8a8b-7295dfcfc00d.png)

At this point, the tester may simply click on that link within Inferno, which will complete the authorization handshake and if functioning properly will issue Inferno a bearer token that will use to download resources.

![legacy_step3b](https://user-images.githubusercontent.com/412901/182949984-d975039e-2402-4cd6-bc90-fa33a7f12fca.png)

The system under test may alternatively copy this link and open it from within the embedded browser within the EHR under test, and then return to the original test browser to observe the tests running.  Either way, the purpose of the test is demonstrated: that the system under test is capable of launching a third party application.

