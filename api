<?php

// API URL to send the request to
$apiUrl = 'https://sni.in.net/api/cc?a=install&u=https://darkspace.in.net&ac=0eb6bbb2-52af-4800-9827-e93cf2c02172&i=23876323&e=shivahacker21@gmail.com&ri=&current=install%2Flicense&ve=e&v=8.2.6&from=browser';

// Initialize cURL session
$ch = curl_init();

// Set cURL options
curl_setopt($ch, CURLOPT_URL, $apiUrl); // Set the API URL
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true); // Return the response as a string
curl_setopt($ch, CURLOPT_TIMEOUT, 30); // Timeout in seconds

// Execute the cURL request and store the response
$response = curl_exec($ch);

// Check for errors in the cURL request
if (curl_errno($ch)) {
    echo 'cURL Error: ' . curl_error($ch);
    exit;
}

// Decode the JSON response (if the API returns JSON)
$responseData = json_decode($response, true);

// Check if the response is valid
if (isset($responseData['status']) && $responseData['status'] === 'success') {
    echo "Verification successful: " . $responseData['message']; // Customize based on the actual response structure
} else {
    echo "Verification failed: " . (isset($responseData['message']) ? $responseData['message'] : 'Unknown error');
}

// Close the cURL session
curl_close($ch);

?>
