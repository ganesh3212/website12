
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="main.css">
    <title>SOF102 Assessment 2</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
          
</head>

<body>
    <div class="website">
        <div class="owner">SISTC</div>

        <div class="description">This is a test website for SOF102 assessment 2.</div>
        <div class="authors">
            <div class="author">
                <div class="photo">
                    <img src="https://scontent.fsyd4-1.fna.fbcdn.net/v/t1.6435-9/117225676_775238043285750_2451457226135514612_n.jpg?stp=dst-jpg_p843x403&_nc_cat=106&ccb=1-7&_nc_sid=174925&_nc_ohc=FDyl51Zf3_0AX-tiRIG&_nc_ht=scontent.fsyd4-1.fna&oh=00_AfA6gPTH7SBI9xvk9jMH0hSdVVDjuzQFEmvac-xUcB45Kw&oe=649B47D5" alt="Author 1 Photo" class="circular-photo">
                </div>
                <div class="details">
                    <div class="name">malai name thaxaina</div>
                    <div class="student-id">S202....</div>
                    <div class="college-email">s2022.....@sistc.nsw.edu.au</div>
                    <div class="teamwork-reflection">"This was a great project and I enjoyed working with my team."</div>
                </div>
            </div>

            <div class="author">
                <div class="photo">
                    <img src="https://scontent.fsyd3-1.fna.fbcdn.net/v/t39.30808-1/305762958_202922898821085_1185920864464903623_n.jpg?stp=dst-jpg_p200x200&_nc_cat=101&ccb=1-7&_nc_sid=7206a8&_nc_ohc=7ERNJ-wnrK8AX_klVF-&_nc_ht=scontent.fsyd3-1.fna&oh=00_AfBGcNcAEZ1n64Q5p7DBg0MjugCBhU7MeHIzo_fPkWjY1w&oe=6481B8FB" alt="Author 2 Photo" class="circular-photo">
                </div>
                <div class="details">
                    <div class="name">Ganesh Bhattarai</div>
                    <div class="student-id">S20230595</div>
                    <div class="college-email">S20230595@sistc.nsw.edu.au</div>
                    <div class="teamwork-reflection">"This was a great project and I enjoyed working with my team."</div>
                </div>
            </div>

            <div class="author">
                <div class="photo">
                    <img src="https://scontent.fsyd3-1.fna.fbcdn.net/v/t39.30808-1/306077672_1769018193462001_2324703879359139384_n.jpg?stp=dst-jpg_p200x200&_nc_cat=101&ccb=1-7&_nc_sid=7206a8&_nc_ohc=HN7EZi6iOucAX9IbuoR&_nc_ht=scontent.fsyd3-1.fna&oh=00_AfDlPVLRmvcCA_gofZd2ish2kOP2a-q4EWDRz9AtHRaTRg&oe=64818D76" alt="Author 3 Photo" class="circular-photo">
                </div>
                <div class="details">
                    <div class="name">name thaxaina</div>
                    <div class="student-id">S202,...</div>
                    <div class="college-email">S202,...@sistc.nsw.edu.au</div>
                    <div class="teamwork-reflection">"This was a great project and I enjoyed working with my team."</div>
                </div>
            </div>
        </div>
        
       <input type="text" id="searchInput" placeholder="Search...">
    <button onclick="searchData()">Search</button>
    <div id="searchResults"></div>
    
    <script>
       function loadData() {
            const xhr = new XMLHttpRequest();
            xhr.open('GET', './data/data.json', true);
            xhr.onload = function () {
                if (xhr.status === 200) {
                    const data = JSON.parse(xhr.responseText);
                    localStorage.setItem('jsonData', JSON.stringify(data));
                } else {
                    console.error('Error loading JSON data:', xhr.status);
                }
            };
            xhr.onerror = function () {
                console.error('Error loading JSON data');
            };
            xhr.send();
        }

       function searchData() {
  const searchInput = document.getElementById("searchInput").value.toLowerCase();
  const searchResults = document.getElementById("searchResults");

  // Clear previous search results
  searchResults.innerHTML = "";

  const jsonData = JSON.parse(localStorage.getItem('jsonData'));

  for (const key in jsonData) {
    if (typeof jsonData[key] === "string" && jsonData[key].toLowerCase().includes(searchInput)) {
      const result = document.createElement("p");
      result.innerText = `${key}: ${jsonData[key]}`;
      searchResults.appendChild(result);
    } else if (Array.isArray(jsonData[key])) {
      const arrayData = jsonData[key];
      for (const item of arrayData) {
        if (typeof item === "object") {
          for (const innerKey in item) {
            if (typeof item[innerKey] === "string" && item[innerKey].toLowerCase().includes(searchInput)) {
              const result = document.createElement("p");
              result.innerText = `${innerKey}: ${item[innerKey]}`;
              searchResults.appendChild(result);
            }
          }
        } else if (typeof item === "string" && item.toLowerCase().includes(searchInput)) {
          const result = document.createElement("p");
          result.innerText = `${key}: ${item}`;
          searchResults.appendChild(result);
        }
      }
    }
  }
}


        window.addEventListener('DOMContentLoaded', () => {
            loadData();
        });

    </script>

        <div id="productTable"></div>


        <div class="product">Products</div>
        <div class="ag-format-container">
            <div class="ag-courses_box">
                <div class="ag-courses_item">
                    <a href="..//main/books.html" class="ag-courses-item_link">
                        <div class="ag-courses-item_bg"></div>
        
                        <div class="ag-courses-item_title">
                            Books
                        </div>
        
                       
                    </a>
                </div>
        
                <div class="ag-courses_item">
                    <a href="..//main/electLab.html" class="ag-courses-item_link">
                        <div class="ag-courses-item_bg"></div>
        
                        <div class="ag-courses-item_title">
                            Electronics 1
                        </div>
        
                     
                    </a>
                </div>
        <div class="ag-courses_item">
            <a href="..//main/electronics.html" class="ag-courses-item_link">
                <div class="ag-courses-item_bg"></div>
        
                <div class="ag-courses-item_title">
                    Electronics 2
                </div>
        
           
            </a>
        </div>
                <div class="ag-courses_item">
                    <a href="..//main/perfume.html" class="ag-courses-item_link">
                        <div class="ag-courses-item_bg"></div>
        
                        <div class="ag-courses-item_title">
                        Perfume
                        </div>
        
                     
                    </a>
                </div>
        
              
        
        
            </div>
        </div>
    </div>

</body>

</html>
