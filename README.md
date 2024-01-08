# Greencast - 24 Hour Green Energy Forecaster

![image](https://user-images.githubusercontent.com/88628203/141161149-82eef6d1-c185-41e7-84e9-34393605652a.png)

Greencast aims to help UK consumers optimise their use of green energy to minimise carbon dioxide emissions. 

Consumers in the UK may schedule their electric power use around times when green energy is forecasted to be available; switching on/plugging in when energy is green and off when it is not. This will help them reduce carbon emissions at a grassroots local level. 

Carbon intensity is used as a primary measure to track carbon emissions from power generation, it shows how much carbon dioxide may be created per kilowatt hour of electric power use.

**Features**

  - indicative forecast of carbon emissions of the electric generation system in the UK, at a local level
  - forecasts shown for 30 minute intervals, for the next 24 hours utilises a 'nowcasting' technique adjusting a short period ahead
      - 24 hour forecast for more accurate information
      - provided at 30 minute intervals, for higher granular scheduling
  - carbon intensity level for locality
  - when to plug in to use green energy 
  - when to plug out when carbon dioxide emissions are high
  - main energy source for the time period selected
  - percentage of main energy source for the time period selected
       
       ![image](https://user-images.githubusercontent.com/88628203/142661464-3d6d6e2c-ed03-4897-9a1f-f3c1aa2a38a9.png)
       
       ![image](https://user-images.githubusercontent.com/88628203/142052039-f0ae1b4e-8c05-4478-b8ba-3eee465cef56.png)

  - percentage of total amount of green energy for the time period selected
  - percentage of total amount of fossil fuel for the time period selected
  - energy generation mix, shown in bar chart form, for the selected 1/2 hour, of different energy generators that contribute to energy supply. Accessed from the 'energy mix' button
 
       ![image](https://user-images.githubusercontent.com/88628203/141859373-13cc7532-3516-4310-9d6e-2b7cc1c34d34.png)

       ![image](https://user-images.githubusercontent.com/88628203/141859481-c7e03304-e777-4daf-b1d0-85d2ef27d275.png)

  - single view app with hidden views with a dark colour theme to reduce battery use and save energy

**Technologies**

  - Swift version  5.0
  - Xcode Version 13.1
  - Core Data 
     -  iOS version 15  
     -  GPX version 1.1
     -  XML version 1.0

**Services**

  - Carbon Intensity API for The United Kingdom of Great Britain, an open API licensed under the CC BY 4.0 license
  - Postcode & Geolocation API for the UK, a free, open source and open data API, MIT licensed
  - iOS Core Data Persistent store
  - iOS Location Manager and Geocoder API services
  
**Permissions**

  - Users will have to give permission to find and use the device's location
  
       ![image](https://user-images.githubusercontent.com/88628203/142052864-6d15263b-9364-4c1f-bc0a-70029896ad29.png)
  
   - If permission to use location services is denied, then users are requested to supply the outercode (first part of UK postcode)
       
       ![image](https://user-images.githubusercontent.com/88628203/142054367-f25f480a-4043-4c93-85b1-3cc8b4b452c2.png)

**Target**

  - Target device; iPhone in portrait mode
  - Intended iOS version: 15+

**Launch**

  The app uses information for UK energy generation and must be provided with a UK location. 
  
  This may be done in one of two ways:

- GPX - for multiple locations

   To simulate UK locations the project comes with a GPX file, integrated into the xcode workspace.
   
      <?xml version="1.0"?>
      <gpx version="1.1" creator="Xcode">
          <wpt lat="51.69276635595619" lon="-0.17803450461617143">
              <name>LocationOne</name>
              <time>2021-10-31T12:01:00Z</time>
          </wpt>

          <wpt lat="52.567480044794316" lon="-1.887361027238978">
              <name>LocationTwo</name>
              <time>2021-10-31T12:02:00Z</time>
          </wpt>

          <wpt lat="53.58566197294269" lon="-2.2538450136520343">
              <name>LocationThree</name>
              <time>2021-10-31T12:03:00Z</time>
          </wpt>

          <wpt lat="56.0377957614273" lon="-3.1931934859564564">
              <name>LocationFour</name>
              <time>2021-10-31T12:04:00Z</time>
          </wpt>

          <wpt lat="51.52193061049775" lon="-3.1724954926025237">
              <name>LocationFive</name>
              <time>2021-10-31T12:05:00Z</time>
          </wpt>
      </gpx>

   To use this ensure the GPX file 'GBLocations' is selected in Xcode: 
   
      Xcode > Product > Scheme > Edit Scheme

   Then enable 'Core Location' to allow location simulation and in the 'Default Location' drop down meu choose 'GBLocations' 
   
   ![image](https://user-images.githubusercontent.com/88628203/140828640-8dd24481-b39a-4f70-bba8-9d19fae937f2.png)

   Locations are set to update at an interval of 1 minute for the locations provided. To view information for different locations, wait 1 minute before tapping the Greencast app's refresh button.

- Location Simulation - for single location

   Select a single UK location in Xcode whilst in run debug mode:
   
      Xcode > Debug > Simulate Location > 'London, England'

 - Note
  
   Delete the app and shut down simulator before re-running a clean build via Xcode to avoid issues with persistent store etc.
   
   Alternatively, you may add a 'Run Script' to 'Build Phases' in your project, and configure it to uninstall the app before running it again. The command for doing this is given in the example below:  
   
   
   ![image](https://user-images.githubusercontent.com/88628203/140829231-4d637f59-b6dc-4523-b930-303e0cc8666d.png)
   
   
   Ensure the simulator is running before running a build with the script shown above.
