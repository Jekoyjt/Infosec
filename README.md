<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Secure Comment System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .comment-box {
            margin-top: 20px;
            padding: 15px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        #comments {
            margin-top: 20px;
        }
        .comment {
            background-color: white;
            padding: 10px;
            margin: 10px 0;
            border-radius: 4px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>

    <h1>Comment System (Secure)</h1>

    <div class="comment-box">
        <textarea id="commentInput" placeholder="Write a comment..."></textarea>
        <button onclick="addComment()">Post Comment</button>
    </div>

    <div id="comments"></div>

    <script>
        function addComment() {
            const input = document.getElementById('commentInput').value.trim();
            if (!input) return; // Prevent empty comments

            const commentsDiv = document.getElementById('comments');
            
            // Create a new div safely
            const commentDiv = document.createElement('div');
            commentDiv.classList.add('comment');
            commentDiv.textContent = input; // Prevents XSS

            commentsDiv.appendChild(commentDiv);
            document.getElementById('commentInput').value = '';
        }
    </script>

</body>
</html>
