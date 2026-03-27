# 🎌 AnimeTrackerFX

Desktop application built with JavaFX that displays seasonal anime data from MyAnimeList.

---

## 📌 Overview

AnimeTrackerFX is a JavaFX-based desktop application that fetches anime data from MyAnimeList using web scraping (JSoup) and displays it in a dynamic table.

The application allows users to browse, sort, and search anime efficiently.

---

## 🚀 Features

* 📡 Fetches anime data from MyAnimeList
* 📊 Displays data in JavaFX TableView
* 🔍 Real-time search/filter
* 🔽 Column sorting (click on headers)
* ⚠️ Error handling (network / HTTP)
* 📝 Logging with Log4j

---

## 📸 Screenshots

### 🔹 Main View (Default Data)

![Main View](images/main-view.png)

Displays anime data exactly as fetched from MyAnimeList.

---

### 🔹 Sorting (Alphabetical Order)

![Sorting](images/sorting.png)

Users can sort data by clicking on column headers (e.g., Title).

---

### 🔹 Search (Filtering Results)

![Search](images/search.png)

Real-time filtering of anime list using search input.

---

## 🛠 Technologies

* Java 17 (LTS)
* JavaFX
* Maven
* JSoup (HTML parsing)
* Log4j (logging)

---

## 📂 Project Structure

```
src/
 └── main/
     ├── java/com/example/jfx/
     │   ├── HelloApplication.java
     │   ├── HelloController.java
     │   ├── DataService.java
     │   └── DataObject.java
     └── resources/
         ├── log4j.xml
         └── log4j.properties
```

---

## ⚙️ How It Works

1. JSoup connects to MyAnimeList website
2. HTML is parsed into Java objects (`DataObject`)
3. Data is displayed in a JavaFX `TableView`
4. User can search and filter results dynamically

---

## 🔗 Seasonal Data Source

The application currently uses a fixed MyAnimeList seasonal URL:

```
Document doc = Jsoup.connect("https://myanimelist.net/anime/season/2023/spring")
        .timeout(6000)
        .get();
```

By modifying the URL, it is possible to fetch anime data from different years and seasons.

### 📌 URL Format

```
https://myanimelist.net/anime/season/{year}/{season}
```

### 📅 Available Seasons

* winter
* spring
* summer
* fall

### ✅ Example URLs

```
https://myanimelist.net/anime/season/2024/winter
https://myanimelist.net/anime/season/2022/summer
https://myanimelist.net/anime/season/2021/fall
```

Currently, changing the season requires modifying the URL directly in the source code.

---

## 🚀 How to Run

### Option 1 – IntelliJ IDEA

1. Open project as Maven project
2. Set Project SDK → Java 17
3. Run:

```
HelloApplication
```

---

### Option 2 – Maven

```
./mvnw clean compile
./mvnw javafx:run
```

---

## ⚠️ Notes

* Requires internet connection
* Web scraping depends on page structure (may break if website changes)
* JavaFX may require VM options depending on setup

---

## 🔮 Future Improvements

* Dynamic season and year selection (without modifying source code)
* GUI controls for selecting anime season
* Open anime link in browser
* Async data loading (non-blocking UI)
* Data caching
* Export to CSV

---

## 👤 Author

Hubert Jabłoński

