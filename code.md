# react-native-super

// App.js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';
import HomeScreen from './screens/HomeScreen';
import DoctorsListScreen from './screens/DoctorsListScreen';
import DoctorProfileScreen from './screens/DoctorProfileScreen';
import AppointmentBookingScreen from './screens/AppointmentBookingScreen';

const Stack = createStackNavigator();

const App = () => {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="DoctorsList" component={DoctorsListScreen} />
        <Stack.Screen name="DoctorProfile" component={DoctorProfileScreen} />
        <Stack.Screen name="AppointmentBooking" component={AppointmentBookingScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
};

export default App;


<hr>
##Home Screen 

// HomeScreen.js
import React from 'react';
import { View, Text, Button } from 'react-native';

const HomeScreen = ({ navigation }) => {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text style={{ fontSize: 24, fontWeight: 'bold', marginBottom: 20 }}>Welcome to the Doctor Consulting App!</Text>
      <Text style={{ fontSize: 16, textAlign: 'center', marginBottom: 40 }}>
        Consult with experienced doctors online. Browse through a wide range of specialties and book appointments conveniently from your mobile device.
      </Text>
      <Button
        title="Browse Doctors"
        onPress={() => navigation.navigate('DoctorsList')}
      />
      <Button
        title="Book Appointment"
        onPress={() => navigation.navigate('AppointmentBooking')}
      />
    </View>
  );
};

export default HomeScreen;

<hr>
## DoctorListScreen
        
        // DoctorsListScreen.js
import React from 'react';
import { View, Text, Button } from 'react-native';

const DoctorsListScreen = ({ navigation }) => {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Doctors List</Text>
      {/* Display the list of doctors here */}
      <Button
        title="View Profile"
        onPress={() => navigation.navigate('DoctorProfile')}
      />
    </View>
  );
};

export default DoctorsListScreen;

<hr>
##Doctor Profile
      
      // DoctorProfileScreen.js
import React from 'react';
import { View, Text, Button } from 'react-native';

const DoctorProfileScreen = ({ navigation }) => {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Doctor's Profile</Text>
      {/* Display the doctor's details here */}
      <Button
        title="Book Appointment"
        onPress={() => navigation.navigate('AppointmentBooking')}
      />
    </View>
  );
};

export default DoctorProfileScreen;

      
<hr>
## Appointment
// AppointmentBookingScreen.js
import React from 'react';
import { View, Text, Button } from 'react-native';

const AppointmentBookingScreen = ({ navigation }) => {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Book an Appointment</Text>
      {/* Add appointment booking form elements here */}
      <Button title="Submit" onPress={() => { /* Handle appointment submission */ }} />
    </View>
  );
};

export default AppointmentBookingScreen;

