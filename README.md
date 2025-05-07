# BookMyShow - A Modern Movie Ticket Booking Platform

BookMyShow is a comprehensive web-based movie ticket booking platform that enables users to browse movies, view showtimes, and book tickets seamlessly. The platform provides an intuitive interface for users to explore current movies, access detailed information about each film, and complete their ticket booking process efficiently.

The platform features a responsive design that works across different devices and screen sizes. It includes real-time seat availability tracking, multiple showtime options, and a streamlined booking process. Users can view movie details including synopsis, director information, and genre classifications, making it easier to make informed decisions about their movie choices.

## Repository Structure
```
.
├── detail-script.js    # Handles movie detail page functionality and ticket booking
├── details.html        # Movie detail page template with showtime information
├── index.html         # Main landing page with movie listings and navigation
├── ost.html          # Additional HTML examples and testing page
├── ost.php           # PHP form handling for user input validation
└── script.js         # Core JavaScript for fetching and displaying movie data
```

## Usage Instructions
### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, or Edge)
- Local web server for PHP functionality
- Internet connection for API access

### Installation
1. Clone the repository to your local machine:
```bash
git clone <repository-url>
```

2. Set up a local web server (for PHP functionality):
#### For Apache:
```bash
# MacOS (using built-in Apache)
sudo apachectl start

# Linux
sudo apt-get install apache2
sudo service apache2 start

# Windows
# Install XAMPP or WampServer
```

3. Configure the web server:
- Place the project files in your web server's document root
- Ensure PHP is enabled on your web server

### Quick Start
1. Navigate to the project directory in your web server
2. Open `index.html` in your web browser
3. Browse the available movies
4. Click on a movie to view details and showtimes
5. Select a showtime and click "Book Tickets" to start the booking process

### More Detailed Examples
#### Browsing Movies
```javascript
// Fetch and display movies
async function fetchMovies() {
    const response = await fetch("https://movie-details-data.onrender.com/movie/get-movie");
    const movies = await response.json();
    // Display movies in the UI
}
```

#### Booking Tickets
```javascript
function bookTickets(movieId, showId, date) {
    // Set booking details in modal
    document.getElementById("modalMovieId").value = movieId;
    document.getElementById("modalShowId").value = showId;
    document.getElementById("modalShowDate").value = date;
    // Show booking modal
}
```

### Troubleshooting
#### API Connection Issues
- **Problem**: Movies not loading
- **Solution**: 
  1. Check internet connection
  2. Verify API endpoint status
  3. Check browser console for errors
  4. Clear browser cache

#### Booking Form Issues
- **Problem**: Form submission errors
- **Solution**:
  1. Ensure all required fields are filled
  2. Validate email format
  3. Check browser console for validation errors
  4. Verify PHP is properly configured on the server

## Data Flow
The application follows a client-server architecture where movie data is fetched from a remote API and displayed to users. The booking process involves user input validation and server-side processing.

```ascii
[Browser] -> [API Request] -> [Movie Data] -> [Display UI]
     |
     v
[User Input] -> [Form Validation] -> [Booking API] -> [Confirmation]
```

Key Component Interactions:
1. Client-side JavaScript fetches movie data from the API
2. Movie details are rendered in the UI using HTML templates
3. User interactions trigger booking modal displays
4. Form submissions are validated client-side
5. Booking requests are processed server-side
6. Confirmation messages are displayed to users
7. Session data is maintained for booking process