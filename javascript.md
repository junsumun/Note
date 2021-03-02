**Javascript**

// Change it using axios
        // const getAllPosts = () => {
        //     var xhr = new XMLHttpRequest();
        //     xhr.onreadystatechange = () => {
        //         if (xhr.readyState == 4 && xhr.status == 200) {
        //             console.log(xhr.response);
        //             xhr.response.Items.forEach(item => {
        //                 generatePost(item, postBoard, attributes);
        //             });
        //         }
        //     };

        //     xhr.open("GET", "api/post", true);
        //     xhr.responseType = "json"
        //     xhr.send();
        // };
        

```javascript
// Attempt to create 2021.03.01 date
const date = new Date(2021, 3, 1);
// However, above code creates one month after march because Month in Javascript starts with 0. ex. 0 == January
```
