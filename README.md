# Ex04 Places Around Me
# Date:2/11/2024
# AIM
To develop a website to display details about the places around my house.

# DESIGN STEPS
## STEP 1
Create a Django admin interface.

## STEP 2
Download your city map from Google.

## STEP 3
Using <map> tag name the map.

## STEP 4
Create clickable regions in the image using <area> tag.

## STEP 5
Write HTML programs for all the regions identified.

## STEP 6
Execute the programs and publish them.

# CODE
```

index.html
       <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>South india</title>
        </head>
        <body>
            
        <style>
         .img{
           margin-left: 1%;
        
           
          
         }
         .img:hover{
            cursor: pointer;
         }
         .tit1{
            font-size: 170px;
            text-align: center;
           
        
         }
         .tit2{
            font-size: 110px;
            text-align: center;
           
         }
         .tit1:hover{
            cursor: default;
         }.tit2:hover{
            cursor: default;
         } 
         body{
             overflow: hidden;
         /* .tamilnadu:hover{
         
          background-color:aqua; Semi-transparent yellow highlight */
        
        }
        
        </style>
        
            <div class="tit1">SOUTH INDIA</div>
            <br><br>
            <center>
            <div>
                <!-- Image Map Generated by https://www.fla-shop.com/image-map/ -->
                {% load static %}
               <center><img src={% static 'Screenshot 2024-12-01 205917.png' %} usemap="#image-map"></center>
        
                <map name="image-map">
                    <area title="tamilnadu" href="tamilnadu.html" coords="424,294,322,357,298,422,321,494,392,435,416,361" shape="poly">
                    <area  title="andhra" href="andhra.html" coords="321,204,319,281,422,300,432,202"  shape="poly">
                    <area  title="karnataka" href="karnataka.html" coords="184,206,313,192,328,351,223,340" shape="poly">
                </map>
        </div>
            
        </body>
        </html>
        
 tamilnadu.html

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tamil Nadu with Disco Border</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url("{% static 'tamilnadu.jpg' %}");
            background-repeat: no-repeat;
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .box {
            width: 300px;
            height: 250px;
            padding: 20px;
            border: 5px solid black;
            box-sizing: border-box;
            background-color: sandybrown;
            position: relative;
            text-align: left;
        }

        h1 {
            font-size: 24px;
            color: #333;
            margin: 0;
        }

        p {
            font-size: 14px;
            color: #555;
            line-height: 1.5;
            margin-top: 10px;
        }

        .next-btn {
            position: absolute;
            top: 50%;
            right: -30px;
            transform: translateY(-50%);
            background-color: #333;
            color: #fff;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 50%;
            font-size: 16px;
        }

        .next-btn:hover {
            background-color: #555;
        }

        @keyframes discoGlow {
            0% { border-color: red; }
            20% { border-color: orange; }
            40% { border-color: yellow; }
            60% { border-color: green; }
            80% { border-color: blue; }
            100% { border-color: purple; }
        }

        .active {
            animation: discoGlow 1s infinite;
        }
    </style>
</head>
<body>
    <div class="box" id="contentBox">
        <h1 id="title">Tamil Nadu</h1>
        <p id="description">Tamil Nadu, located in the southern part of India, is known for its rich cultural heritage, ancient temples, and vibrant traditions. The state is famous for its classical music, dance, and Tamil literature. Chennai is the capital city of Tamil Nadu, and the state is also home to the famous hill stations of Ooty and Kodaikanal.</p>
        <button class="next-btn" onclick="showNext()">&#9654;</button>
    </div>
    <script>
        const content = [
            {
                title: "Tamil Nadu",
                description: "Tamil Nadu, located in the southern part of India, is known for its rich cultural heritage, ancient temples, and vibrant traditions. The state is famous for its classical music, dance, and Tamil literature. Chennai is the capital city of Tamil Nadu, and the state is also home to the famous hill stations of Ooty and Kodaikanal."
            },
            {
                title: "Coastline and Cuisine",
                description: "The state boasts a long coastline along the Bay of Bengal and is renowned for its beautiful beaches such as Marina Beach and Covelong Beach. Tamil Nadu is also famous for its traditional cuisine, especially dishes like dosa, idli, sambar, and biryani."
            },
            {
                title: "Economy and Tourism",
                description: "Tamil Nadu's economy is one of the largest in India, with key industries like automobile manufacturing, textiles, agriculture, and information technology. The state also has a thriving tourism sector, with visitors flocking to its historical sites, temples, and natural beauty."
            },
            {
                title: "Traditional Foods",
                description: "Idli, dosa, sambar, pongal, vada, murukku, parippu payasam, filter coffee - a culinary journey through Tamil Nadu's diverse flavors."
            },
            {
                title: "Tradition",
                description: "Tamil Nadu, a land steeped in tradition, boasts a rich cultural heritage. From ancient temples and classical dance forms like Bharatanatyam to intricate kolam designs and vibrant festivals like Pongal, the state's traditions continue to enchant."
            }
        ];

        let currentIndex = 0;

        function showNext() {
            currentIndex = (currentIndex + 1) % content.length;
            document.getElementById("title").textContent = content[currentIndex].title;
            document.getElementById("description").textContent = content[currentIndex].description;

            const contentBox = document.getElementById("contentBox");
            contentBox.classList.toggle('active');
        }
    </script>
</body>
</html>

andhra.html

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Andhra Pradesh</title>
    <style>
        /* General body styles */
        body {
            font-family: Arial, sans-serif;
            background-image: url("{% static 'andhra.jpg' %}");
            background-repeat: no-repeat;
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        /* Box container */
        .box {
            width: 300px;
            height: 250px;
            padding: 20px;
            border: 5px solid black;
            box-sizing: border-box;
            background-color: rgb(6, 103, 56);
            position: relative;
            text-align: left;
        }

        /* Title styling */
        h1 {
            font-size: 24px;
            color: red;
            margin: 0;
        }

        /* Paragraph styling */
        p {
            font-size: 14px;
            color: white;
            line-height: 1.5;
            margin-top: 10px;
        }

        /* Next button styling */
        .next-btn {
            position: absolute;
            top: 50%;
            right: -30px;
            transform: translateY(-50%);
            background-color: #333;
            color: #dbe60c;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 50%;
            font-size: 16px;
        }

        .next-btn:hover {
            background-color: #555;
        }

        /* Disco border animation */
        @keyframes discoGlow {
            0% { border-color: red; }
            20% { border-color: orange; }
            40% { border-color: yellow; }
            60% { border-color: green; }
            80% { border-color: blue; }
            100% { border-color: purple; }
        }

        /* Active class for disco effect */
        .active {
            animation: discoGlow 1s infinite;
        }
    </style>
</head>
<body>
    <div class="box" id="contentBox">
        <h1 id="title">Andhra Pradesh</h1>
        <p id="description">Andhra Pradesh, a state in southern India, is known for its rich cultural heritage, historical monuments, and delicious cuisine. The state is home to ancient temples like the Lepakshi temple, beautiful beaches like Visakhapatnam, and the vibrant city of Hyderabad.</p>
        <button class="next-btn" onclick="showNext()">&#9654;</button>
    </div>

    <script>
        // Content array to display in the box
        const content = [
            {
                title: "Andhra Pradesh",
                description: "Andhra Pradesh, a state in southern India, is known for its rich cultural heritage, historical monuments, and delicious cuisine. The state is home to ancient temples like the Lepakshi temple, beautiful beaches like Visakhapatnam, and the vibrant city of Hyderabad. "
            },
            {
                title: "Coastline and Cuisine",
                description: "Andhra Pradesh boasts a stunning coastline along the Bay of Bengal, offering pristine beaches like Visakhapatnam and Machilipatnam. Its cuisine is renowned for its fiery flavors, with dishes like Hyderabadi Biryani, Andhra Chicken Curry, and Mirchi Bajji.   "
            },
            {
                title: "Economy and Tourism",
                description: "Andhra Pradesh's economy is driven by agriculture, information technology, and manufacturing sectors. The state boasts a strong agricultural base, producing rice, sugarcane, and cotton. Cities like Hyderabad and Visakhapatnam are major IT hubs"
            },
            {
                title: "Traditional Foods",
                description: "Andhra Pradesh boasts a rich culinary heritage, known for its bold flavors and spicy dishes. Some of the most popular traditional foods include:Hyderabadi Biryani,Andhra Chicken Curry,Pulihora,Pesarattu,Gongura Pachadi."
            },
            {
                title: "Tradition",
                description: "Andhra Pradesh, a state steeped in history and culture, boasts a vibrant tapestry of traditions. From the ancient temples of Lepakshi to the bustling city of Hyderabad, the state offers a unique blend of old and new."
            }
        ];

        // Index to track the current content
        let currentIndex = 0;

        // Function to show the next content
        function showNext() {
            currentIndex = (currentIndex + 1) % content.length; // Cycle through the array
            document.getElementById("title").textContent = content[currentIndex].title;
            document.getElementById("description").textContent = content[currentIndex].description;

            // Toggle disco border effect
            const contentBox = document.getElementById("contentBox");
            contentBox.classList.toggle('active');
        }
    </script>
</body>
</html>

karnataka.html

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Karnataka</title>
    <style>
        /* General body styles */
        body {
            font-family: Arial, sans-serif;
            background-image: url("{% static 'new.karnataka.jpeg' %}");
            background-repeat: no-repeat;
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        /* Box container */
        .box {
            width: 300px;
            height: 250px;
            padding: 20px;
            border: 5px solid black;
            box-sizing: border-box;
            background-color: wheat;
            position: relative;
            text-align: left;
        }

        /* Title styling */
        h1 {
            font-size: 24px;
            color: #333;
            margin: 0;
        }

        /* Paragraph styling */
        p {
            font-size: 14px;
            color: #555;
            line-height: 1.5;
            margin-top: 10px;
        }

        /* Next button styling */
        .next-btn {
            position: absolute;
            top: 50%;
            right: -30px;
            transform: translateY(-50%);
            background-color: #333;
            color: #fff;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 50%;
            font-size: 16px;
        }

        .next-btn:hover {
            background-color: #555;
        }

        /* Disco border animation */
        @keyframes discoGlow {
            0% { border-color: red; }
            20% { border-color: orange; }
            40% { border-color: yellow; }
            60% { border-color: green; }
            80% { border-color: blue; }
            100% { border-color: purple; }
        }

        /* Active class for disco effect */
        .active {
            animation: discoGlow 1s infinite;
        }
    </style>
</head>
<body>
    <div class="box" id="contentBox">
        <h1 id="title">Karnataka</h1>
        <p id="description">Karnataka, a southern Indian gem, boasts ancient temples like Belur and Halebidu, serene hill stations like Coorg and Chikmagalur, and pristine beaches. Its vibrant culture includes classical music, Yakshagana dance, and Kannada literature. Bengaluru, the IT hub, adds a cosmopolitan touch to this diverse state.</p>
        <button class="next-btn" onclick="showNext()">&#9654;</button>
    </div>

    <script>
        // Content array to display in the box
        const content = [
            {
                title: "Karnataka",
                description: "Karnataka, a southern Indian gem, boasts ancient temples like Belur and Halebidu, serene hill stations like Coorg and Chikmagalur, and pristine beaches. Its vibrant culture includes classical music, Yakshagana dance, and Kannada literature."
            },
            {
                title: "Coastline and Cuisine",
                description: "Karnataka's coastline, though shorter than its neighbor Kerala, offers pristine beaches like Gokarna and Malpe. Its cuisine is a delightful blend of flavors, with dishes like masala dosa, idli, and vadas being popular breakfast options."
            },
            {
                title: "Economy and Tourism",
                description: "Karnataka's economy is robust and diverse, driven by sectors like IT, biotechnology, and manufacturing. Bengaluru, the IT capital of India, is a major contributor to the state's economic growth."
            },
            {
                title: "Traditional Foods",
                description: "Karnataka boasts a diverse culinary scene, with dishes influenced by various regions and cultures. Here are some of the most popular traditional foods: Bisi Bele Bath, Mysore Pak, Idli and Dosa, Ragi Mudde, Jolada Rotti, Mangalorean Fish Curry, Mysore Masala Dosa."
            },
            {
                title: "Tradition",
                description: "Karnataka, a state rich in history and culture, boasts a diverse tapestry of traditions. From the ancient temples of Hampi to the serene beauty of Coorg, the state offers a unique blend of old and new."
            }
        ];

        // Index to track the current content
        let currentIndex = 0;

        // Function to show the next content
        function showNext() {
            currentIndex = (currentIndex + 1) % content.length; // Cycle through the array
            document.getElementById("title").textContent = content[currentIndex].title;
            document.getElementById("description").textContent = content[currentIndex].description;

            // Toggle disco border effect
            const contentBox = document.getElementById("contentBox");
            contentBox.classList.toggle('active');
        }
    </script>
</body>
</html>


```

# OUTPUT
![Screenshot 2024-12-07 205734](https://github.com/user-attachments/assets/84e92785-786d-4887-9d10-006533e09c01)
![Screenshot 2024-12-07 213718](https://github.com/user-attachments/assets/c999f197-16e5-4c45-98b3-5193fd0cbde9)
![Screenshot 2024-12-07 214312](https://github.com/user-attachments/assets/ce9291ab-a7e5-4bfc-8d08-1874b23fa56d)
![Screenshot 2024-12-07 214652](https://github.com/user-attachments/assets/894acae3-42c4-4a12-b32b-3a71fc846b28)






# RESULT
The program for implementing image maps using HTML is executed successfully.
+
