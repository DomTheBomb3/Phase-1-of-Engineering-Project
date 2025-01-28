# Phase-1-of-Engineering-Project
This is the phase 1 code so if I mess up it, I can fall back on this version.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>News Rating</title>
    <style>
        body { width: 400px; text-align: center; font-family: Arial, sans-serif; }
        .news-table { display: none; margin: auto; border-collapse: collapse; width: 100%; }
        .news-table th, .news-table td { border: 1px solid black; padding: 8px; }
        .news-table th { background-color: grey; }
    </style>
</head>
<body>
    <h2>News Rating System</h2>

    <table id="nbcTable" class="news-table">
        <tr><th colspan="2">NBC News Ratings</th></tr>
        <tr><td>Credibility</td><td></td></tr>
        <tr><td>Reliability</td><td></td></tr>
        <tr><td>Bias</td><td></td></tr>
        <tr><td>Community Rating</td><td></td></tr>
        <tr><td>Professional Rating</td><td></td></tr>
        <tr><td>Overall Rating</td><td></td></tr>
    </table>

    <table id="foxTable" class="news-table">
        <tr><th colspan="2">FOX News Ratings</th></tr>
        <tr><td>Credibility</td><td></td></tr>
        <tr><td>Reliability</td><td></td></tr>
        <tr><td>Bias</td><td></td></tr>
        <tr><td>Community Rating</td><td></td></tr>
        <tr><td>Professional Rating</td><td></td></tr>
        <tr><td>Overall Rating</td><td></td></tr>
    </table>

    <table id="cnnTable" class="news-table">
        <tr><th colspan="2">CNN News Ratings</th></tr>
        <tr><td>Credibility</td><td></td></tr>
        <tr><td>Reliability</td><td></td></tr>
        <tr><td>Bias</td><td></td></tr>
        <tr><td>Community Rating</td><td></td></tr>
        <tr><td>Professional Rating</td><td></td></tr>
        <tr><td>Overall Rating</td><td></td></tr>
    </table>

    <table id="wsjTable" class="news-table">
        <tr><th colspan="2">Wall Street Journal Ratings</th></tr>
        <tr><td>Credibility</td><td></td></tr>
        <tr><td>Reliability</td><td></td></tr>
        <tr><td>Bias</td><td></td></tr>
        <tr><td>Community Rating</td><td></td></tr>
        <tr><td>Professional Rating</td><td></td></tr>
        <tr><td>Overall Rating</td><td></td></tr>
    </table>

    <table id="nytTable" class="news-table">
        <tr><th colspan="2">New York Times Ratings</th></tr>
        <tr><td>Credibility</td><td></td></tr>
        <tr><td>Reliability</td><td></td></tr>
        <tr><td>Bias</td><td></td></tr>
        <tr><td>Community Rating</td><td></td></tr>
        <tr><td>Professional Rating</td><td></td></tr>
        <tr><td>Overall Rating</td><td></td></tr>
    </table>

    <table id="cbsTable" class="news-table">
        <tr><th colspan="2">CBS News Ratings</th></tr>
        <tr><td>Credibility</td><td></td></tr>
        <tr><td>Reliability</td><td></td></tr>
        <tr><td>Bias</td><td></td></tr>
        <tr><td>Community Rating</td><td></td></tr>
        <tr><td>Professional Rating</td><td></td></tr>
        <tr><td>Overall Rating</td><td></td></tr>
    </table>

    <script src="js/popup.js"></script>
</body>
</html>

document.addEventListener("DOMContentLoaded", function () {
    // Get the current tab URL
    chrome.tabs.query({ active: true, currentWindow: true }, function (tabs) {
        let url = tabs[0].url;

        // Hide all tables first
        let tables = document.querySelectorAll(".news-table");
        tables.forEach(table => table.style.display = "none");

        // Match URL to a table
        if (url.includes("nbcnews.com")) {
            document.getElementById("nbcTable").style.display = "table";
        } else if (url.includes("foxnews.com")) {
            document.getElementById("foxTable").style.display = "table";
        } else if (url.includes("cnn.com")) {
            document.getElementById("cnnTable").style.display = "table";
        } else if (url.includes("wsj.com")) {
            document.getElementById("wsjTable").style.display = "table";
        } else if (url.includes("nytimes.com")) {
            document.getElementById("nytTable").style.display = "table";
        } else if (url.includes("cbsnews.com")) {
            document.getElementById("cbsTable").style.display = "table";
        } else {
            document.body.innerHTML += "<p>Not a supported news site.</p>";
        }
    });
});

{
    "manifest_version": 3,
    "name": "News Rating Extension",
    "description": "Displays a rating table for different news websites.",
    "version": "1.0",
    "action": {
      "default_popup": "popup.html",
      "default_icon": {
        "16": "images/icon16.png",
        "48": "images/icon48.png",
        "128": "images/icon128.png"
      }
    },
    "permissions": ["activeTab"]
  }
