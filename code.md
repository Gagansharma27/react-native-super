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

##Home Screen 
<hr>
