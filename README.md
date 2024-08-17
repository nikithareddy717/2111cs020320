import React, { useState } from 'react';

const ClientInformationForm = () => {
  const [formData, setFormData] = useState({
    companyName: '',
    clientID: '',
    clientSecret: '', // Consider removing this field from the form
    ownerName: '',
    ownerEmail: '',
    rollNo: '',
  });

  const handleChange = (event) => {
    setFormData({
      ...formData,
      [event.target.name]: event.target.value,
    });
  };

  const handleSubmit = (event) => {
    event.preventDefault();

    // **Security Warning:** Never store sensitive information like clientSecret in plain text.
    // Consider using a secure backend for authentication and data storage.
    console.log('Form submitted:', formData); // For demonstration only

    // Perform any additional actions with the form data (e.g., send to a backend)
  };

  return (
    <form onSubmit={handleSubmit}>
      <label htmlFor="companyName">Company Name:</label>
      <input
        type="text"
        id="companyName"
        name="companyName"
        value={formData.companyName}
        onChange={handleChange}
        required
      />

      <label htmlFor="clientID">Client ID:</label>
      <input
        type="text"
        id="clientID"
        name="clientID"
        value={formData.clientID}
        onChange={handleChange}
        required
      />

      {/* Remove clientSecret field for security */}
      {/* <label htmlFor="clientSecret">Client Secret:</label>
      <input
        type="password" // Consider using a more secure input type
        id="clientSecret"
        name="clientSecret"
        value={formData.clientSecret}
        onChange={handleChange}
      /> */}

      <label htmlFor="ownerName">Owner Name:</label>
      <input
        type="text"
        id="ownerName"
        name="ownerName"
        value={formData.ownerName}
        onChange={handleChange}
        required
      />

      <label htmlFor="ownerEmail">Owner Email:</label>
      <input
        type="email"
        id="ownerEmail"
        name="ownerEmail"
        value={formData.ownerEmail}
        onChange={handleChange}
        required
      />

      <label htmlFor="rollNo">Roll No.:</label>
      <input
        type="text"
        id="rollNo"
        name="rollNo"
        value={formData.rollNo}
        onChange={handleChange}
      />

      <button type="submit">Submit</button>
    </form>
  );
};

export default ClientInformationForm;
