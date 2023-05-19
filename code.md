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
      
<hr>
## Doctor data
      import React from 'react';
import { View, Text, Button, FlatList } from 'react-native';

const doctorsData = [
  {
    id: 1,
    name: 'Dr. John Doe',
    specialty: 'Cardiology',
    experience: '10 years',
  },
  {
    id: 2,
    name: 'Dr. Jane Smith',
    specialty: 'Dermatology',
    experience: '8 years',
  },
  {
    id: 3,
    name: 'Dr. Michael Johnson',
    specialty: 'Orthopedics',
    experience: '12 years',
  },
];

const DoctorsListScreen = ({ navigation }) => {
  const renderDoctorItem = ({ item }) => {
    return (
      <View style={{ marginVertical: 10 }}>
        <Text>Name: {item.name}</Text>
        <Text>Specialty: {item.specialty}</Text>
        <Text>Experience: {item.experience}</Text>
        <Button
          title="View Profile"
          onPress={() => navigation.navigate('DoctorProfile', { doctor: item })}
        />
      </View>
    );
  };

  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Doctors List</Text>
      <FlatList
        data={doctorsData}
        renderItem={renderDoctorItem}
        keyExtractor={(item) => item.id.toString()}
      />
    </View>
  );
};

export default DoctorsListScreen;
      
<hr>
##Claim Screen
      
import React, { useState } from 'react';
import { View, Text, TextInput, Button } from 'react-native';

const ClaimScreen = () => {
  const [billAmount, setBillAmount] = useState('');
  const [billDescription, setBillDescription] = useState('');

  const handleSubmit = () => {
    // Perform the submission logic here
    // You can send the billAmount and billDescription to a server or store them locally
    // Display a success message or navigate to a confirmation screen
  };

  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center', paddingHorizontal: 20 }}>
      <Text style={{ fontSize: 24, fontWeight: 'bold', marginBottom: 20 }}>Claim Your Health Bills</Text>
      <TextInput
        style={{ height: 40, width: '100%', borderColor: 'gray', borderWidth: 1, marginBottom: 20, paddingHorizontal: 10 }}
        placeholder="Bill Amount"
        keyboardType="numeric"
        value={billAmount}
        onChangeText={text => setBillAmount(text)}
      />
      <TextInput
        style={{ height: 80, width: '100%', borderColor: 'gray', borderWidth: 1, marginBottom: 40, paddingHorizontal: 10 }}
        placeholder="Bill Description"
        multiline
        numberOfLines={3}
        value={billDescription}
        onChangeText={text => setBillDescription(text)}
      />
      <Button
        title="Submit Claim"
        onPress={handleSubmit}
      />
    </View>
  );
};

export default ClaimScreen;
        
<hr>
Picker
 
const [selectedHospital, setSelectedHospital] = useState('');
        
        
 const handleSubmit = () => {
    // Perform the submission logic here
    // You can send the billAmount and billDescription to a server or store them locally
    // Display a success message or navigate to a confirmation screen
  };
        
        
 <Picker
        style={{ height: 40, width: '100%', marginBottom: 40 }}
        selectedValue={selectedHospital}
        onValueChange={itemValue => setSelectedHospital(itemValue)}
      >
        <Picker.Item label="Select Hospital" value="" />
        <Picker.Item label="Hospital A" value="Hospital A" />
        <Picker.Item label="Hospital B" value="Hospital B" />
        <Picker.Item label="Hospital C" value="Hospital C" />
        {/* Add more hospitals as needed */}
 </Picker>


        
<hr>
        
Success Screen 
 
import React from 'react';
import { View, Text, Button } from 'react-native';

const SuccessScreen = ({ navigation }) => {
  const handleContinue = () => {
    // Perform any necessary actions upon successful submission
    // You can navigate to another screen or reset the claim form
    navigation.navigate('Home');
  };

  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center', paddingHorizontal: 20 }}>
      <Text style={{ fontSize: 24, fontWeight: 'bold', marginBottom: 20 }}>Claim Submitted Successfully!</Text>
      <Text style={{ fontSize: 16, textAlign: 'center', marginBottom: 40 }}>
        Your health bill has been successfully submitted. We will review your claim and process it accordingly.
      </Text>
      <Button
        title="Continue"
        onPress={handleContinue}
      />
    </View>
  );
};

export default SuccessScreen;
        
        
<hr>
##Appointment Booking
import React, { useState } from 'react';
import { View, Text, TextInput, Button } from 'react-native';

const AppointmentBookingScreen = ({ navigation }) => {
  const [time, setTime] = useState('');
  const [place, setPlace] = useState('');
  const [patientName, setPatientName] = useState('');

  const handleAppointmentSubmission = () => {
    // Perform the appointment submission logic here
    // You can use the values of time, place, and patientName to save or send the appointment details
    // Display a success message or navigate to a confirmation screen
  };

  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Book an Appointment</Text>
      <TextInput
        style={{ height: 40, width: '80%', borderColor: 'gray', borderWidth: 1, marginVertical: 10, paddingHorizontal: 10 }}
        placeholder="Time"
        value={time}
        onChangeText={text => setTime(text)}
      />
      <TextInput
        style={{ height: 40, width: '80%', borderColor: 'gray', borderWidth: 1, marginVertical: 10, paddingHorizontal: 10 }}
        placeholder="Place"
        value={place}
        onChangeText={text => setPlace(text)}
      />
      <TextInput
        style={{ height: 40, width: '80%', borderColor: 'gray', borderWidth: 1, marginVertical: 10, paddingHorizontal: 10 }}
        placeholder="Patient Name"
        value={patientName}
        onChangeText={text => setPatientName(text)}
      />
      <Button title="Submit" onPress={handleAppointmentSubmission} />
    </View>
  );
};

export default AppointmentBookingScreen;
