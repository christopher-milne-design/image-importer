# CAC Image Builder

A social media toolkit for creating customized images with the Canada Council for the Arts branding. Built with vanilla HTML, CSS, and JavaScript.

## Features

- **Bilingual Support**: Toggle between French and English
- **Dual Image Generation**: 
  - Image 1: Upload your own photo with art block overlay
  - Image 2: Colored background with slogan and logo
- **Format Options**: Choose between Post (1080x1440) or Story (1080x1920)
- **Color Themes**: 5 vibrant color options
- **Image Manipulation**: Pan/drag uploaded images to reposition
- **Download**: Export both images as high-quality JPEGs

## Running the Application

### Option 1: Simple HTTP Server (Python)

```bash
cd cac-image-builder
python3 -m http.server 8000
```

Then open: http://localhost:8000

### Option 2: Node.js HTTP Server

```bash
npm install -g http-server
cd cac-image-builder
http-server -p 8000
```

### Option 3: VS Code Live Server

1. Install the "Live Server" extension in VS Code
2. Right-click `index.html` and select "Open with Live Server"

### Option 4: ASP.NET Core (.NET 6+)

If you want to serve this with .NET, create a minimal API:

```bash
dotnet new web -n CACImageBuilder
cd CACImageBuilder
# Copy index.html, styles.css, and app.js into wwwroot/
# Update Program.cs (see below)
dotnet run
```

**Program.cs:**
```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.UseDefaultFiles();
app.UseStaticFiles();

app.Run();
```

## Project Structure

```
cac-image-builder/
├── index.html      # Main HTML structure
├── styles.css      # All styling (Apple-inspired design)
├── app.js          # Canvas manipulation & image generation
└── README.md       # This file
```

## How It Works

1. **Canvas API**: Uses HTML5 Canvas for real-time image composition
2. **Client-Side Processing**: All image manipulation happens in the browser
3. **Remote Assets**: Logos and overlay graphics loaded from imgur CDN
4. **FileReader API**: Uploads and processes user images locally
5. **Data URLs**: Downloads generated images via canvas.toDataURL()

## Browser Compatibility

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support  
- Safari: ✅ Full support
- Mobile browsers: ✅ Touch-enabled panning

## Technologies Used

- HTML5 Canvas
- CSS3 (CSS Variables, Grid, Flexbox)
- Vanilla JavaScript (ES6+)
- FileReader API
- Canvas toDataURL for image export

## Next Steps for .NET Integration

To integrate with ASP.NET Core:

1. **Static File Serving**: Use `app.UseStaticFiles()` middleware
2. **Razor Pages**: Convert to `.cshtml` for server-side rendering
3. **API Endpoints**: Add endpoints for server-side image processing if needed
4. **Database**: Store user creations or analytics
5. **Authentication**: Add user accounts with ASP.NET Identity

## License

Original design by Canada Council for the Arts.
# image-importer
