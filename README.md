# IDEA Hacks 2024 
# Inspiration

Due to doctor burnout and natural biases, particularly in a post COVID-19 era, patients may not always receive a consistent quality of care. Additionally, at-home telehealth services are currently limited by cost and accessibility. Current solutions aren't nearly as accessible and affordable as necessary for the larger audience, as they often relying on expensive devices and trained staff, or are confined to processes that are not easily adaptable to a range of conditions (e.g. elderly patients, visual impairments). This issue is compounded in rural areas, typically where veterans reside, where healthcare is just as important as in the big cities, if not more. Additionally, miscommunication between patient and physician due to language barriers further limits the connections between medical professionals and patients. As in-person medical facilities create enviornments that may be a source of infection, telemedicine reduces disease spread, resulting in a smoother flow of patients through the healthcare system.

# What it does

To mitigate this, we propose an AI powered assistant that is both affordable and highly efficient in delivering consistent, up-to-date with current literature, instant, and understandable initial diagnosis. We implemented this in the form of a hardware assistant (shaped like a friendly duck!) that is also affordable enough to be implemented in any home. We envision Ducktor supporting taking vitals, engaging in conversation with patients and analyzing data to provide to both patients for initial diagnosis and doctors to aid and streamline their diagnosing.

# How we built it

We collected audio input from the user via a microphone connected to an ESP32. We sent this data to one of our Flask web servers, where the PCM signals are converted into .wav audio and transcribed into text. This text is then relayed to another web server where we utilize OpenAI's technology to determine potential diagnoses from the complains of the patient, and respond with an initial diagnosis, some home remedies, and a deeper explanation of what this means and how they should proceed with their healthcare. The information is then relayed back to the microcontroller and displayed on a screen and spoken out loud.

# Challenges

We were unable to achieve a stable WiFi connection with IEEE_5G on our ESP32, which rendered us unable to send HTTP requests to our server. This delayed the implementation of communication between our device and the cloud processing where the magic occurs, forcing us to prioritize features. We also encountered hardware issues between faulty boards and incompatibility between devices.

# Accomplishments

We were able to make data sent from the device to the server secure and encrypted to ensure patient privacy throughout these exchanges. We were also able to take most of the processing to the cloud, so the device can remain affordable, small, and accessible to patients across the world. In addition, each of the available features: pulse detection, audio input, and text-to-display, function on their own. 
