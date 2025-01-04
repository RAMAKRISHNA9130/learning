<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Instagram Clone</title>
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #fafafa;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        header {
            width: 100%;
            background-color: #ffffff;
            padding: 10px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        header .logo {
            font-size: 24px;
            font-weight: bold;
            color: #333;
        }

        header .search input {
            padding: 8px;
            width: 200px;
            border-radius: 5px;
            border: 1px solid #ddd;
        }

        header .profile img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
        }

        /* Layout */
        .container {
            display: flex;
            justify-content: space-between;
            width: 80%;
            max-width: 1200px;
            margin-top: 20px;
        }

        .sidebar {
            width: 15%;
            background-color: #fff;
            padding: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .sidebar ul {
            list-style: none;
        }

        .sidebar ul li {
            margin-bottom: 10px;
        }

        .sidebar ul li a {
            text-decoration: none;
            color: #333;
            font-size: 18px;
        }

        /* Feed */
        .feed {
            width: 60%;
        }

        .post {
            background-color: #fff;
            margin-bottom: 20px;
            padding: 15px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        .post-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .post-header .user-info {
            margin-left: 10px;
        }

        .post-header .user-info strong {
            font-size: 16px;
        }

        .post-header .user-info p {
            font-size: 14px;
            color: #777;
        }

        .post-img {
            width: 100%;
            height: auto;
            margin-top: 10px;
            border-radius: 8px;
        }

        .post-footer {
            margin-top: 10px;
            display: flex;
            justify-content: space-between;
        }

        .like-btn, .comment-btn {
            background-color: #3897f0;
            color: #fff;
            border: none;
            padding: 8px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .like-btn:hover, .comment-btn:hover {
            background-color: #2a6cbf;
        }

        .like-btn {
            width: 80px;
        }

        .comment-btn {
            width: 100px;
        }

        /* Right Sidebar */
        .right-sidebar {
            width: 20%;
        }

        .suggested-users {
            background-color: #fff;
            padding: 15px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        .suggested-user {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .suggested-user img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
        }

        .suggested-user .user-info {
            margin-left: 10px;
        }

        .suggested-user .user-info strong {
            font-size: 16px;
        }

        .suggested-user .user-info p {
            font-size: 14px;
            color: #777;
        }

        .follow-btn {
            background-color: #3897f0;
            color: #fff;
            border: none;
            padding: 8px 12px;
            border-radius: 5px;
            cursor: pointer;
        }

        .follow-btn:hover {
            background-color: #2a6cbf;
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header>
        <div class="logo">InstaClone</div>
        <div class="search">
            <input type="text" placeholder="Search...">
        </div>
        <div class="profile">
            <img src="https://via.placeholder.com/40" alt="Profile">
        </div>
    </header>

    <!-- Main Content Section -->
    <div class="container">
        <div class="sidebar">
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Explore</a></li>
                <li><a href="#">Messages</a></li>
                <li><a href="#">Notifications</a></li>
                <li><a href="#">Profile</a></li>
            </ul>
        </div>

        <!-- Posts Section -->
        <div class="feed">
            <!-- Post 1 -->
            <div class="post">
                <div class="post-header">
                    <img src="https://via.placeholder.com/40" alt="User" class="user-img">
                    <div class="user-info">
                        <strong>John Doe</strong>
                        <p>@john_doe</p>
                    </div>
                    <button class="more-btn">...</button>
                </div>
                <img src="https://via.placeholder.com/500x400" alt="Post Image" class="post-img">
                <div class="post-footer">
                    <button class="like-btn" id="like-btn-1">Like</button>
                    <span id="like-count-1">10 likes</span>
                    <button class="comment-btn">Comment</button>
                </div>
            </div>

            <!-- Post 2 -->
            <div class="post">
                <div class="post-header">
                    <img src="https://via.placeholder.com/40" alt="User" class="user-img">
                    <div class="user-info">
                        <strong>Jane Smith</strong>
                        <p>@jane_smith</p>
                    </div>
                    <button class="more-btn">...</button>
                </div>
                <img src="https://via.placeholder.com/500x400" alt="Post Image" class="post-img">
                <div class="post-footer">
                    <button class="like-btn" id="like-btn-2">Like</button>
                    <span id="like-count-2">5 likes</span>
                    <button class="comment-btn">Comment</button>
                </div>
            </div>
        </div>

        <!-- Right Sidebar Section -->
        <div class="right-sidebar">
            <div class="suggested-users">
                <h4>Suggested Users</h4>
                <div class="suggested-user">
                    <img src="https://via.placeholder.com/40" alt="User" class="user-img">
                    <div class="user-info">
                        <strong>Mike</strong>
                        <p>@mike</p>
                    </div>
                    <button class="follow-btn">Follow</button>
                </div>
                <div class="suggested-user">
                    <img src="https://via.placeholder.com/40" alt="User" class="user-img">
                    <div class="user-info">
                        <strong>Sarah</strong>
                        <p>@sarah</p>
                    </div>
                    <button class="follow-btn">Follow</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Like Button Functionality
        const likeButtons = document.querySelectorAll('.like-btn');
        likeButtons.forEach((button, index) => {
            button.addEventListener('click', () => {
                const likeCountElement = document.getElementById(`like-count-${index + 1}`);
                let likeCount = parseInt(likeCountElement.textContent.split(' ')[0]);
                if (button.textContent === 'Like') {
                    button.textContent = 'Unlike';
                    likeCount++;
                } else {
                    button.textContent = 'Like';
                    likeCount--;
                }
                likeCountElement.textContent = `${likeCount} likes`;
            });
        });
    </script>
</body>
</html>
