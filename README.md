# TabMask

### TabMask - The program to disguise your tabs
Has your teacher looking over your shoulder, having no idea why your "Learning" tab has the title of "Fun Games Free" and the icon of a game controller? You're in luck.

<h2 align="center">Features</h2>

- Presets
- Tab icon changes per preset
- Tab title changes per preset

<h2 align="center">Tutorial - How to run and tips</h2>

To use TabMask, drag the following link to your bookmarks bar in an empty area:
<a href="javascript:(function()%7B%2F%2F Define presets%0Aconst presets %3D %5B%0A  %7B%0A    title%3A "Clever preset"%2C%0A    favicon%3A "https%3A%2F%2Fassets.clever.com%2Ffavicon.ico"%2C%0A    pageTitle%3A "Clever"%0A  %7D%2C%0A  %7B%0A    title%3A "ClassLink preset"%2C%0A    favicon%3A "https%3A%2F%2Fplay-lh.googleusercontent.com%2Fujsa1M8GdT-fo-GfPazpUwgPXVWEOWKUgKZk-SdnUhmcL3opS24MiHe6ypEgqxGpllw"%2C%0A    pageTitle%3A "ClassLink"%0A  %7D%2C%0A  %7B%0A    title%3A "Google Classroom preset"%2C%0A    favicon%3A "https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2F5%2F59%2FGoogle_Classroom_Logo.png"%2C%0A    pageTitle%3A "Google Classroom"%0A  %7D%2C%0A  %7B%0A    title%3A "i-Ready Preset"%2C%0A    favicon%3A "https%3A%2F%2Flogin.i-ready.com%2Ffavicon.ico"%2C%0A    pageTitle%3A "i-Ready"%0A  %7D%2C%0A  %7B%0A    title%3A "McGraw-Hill preset"%2C%0A    favicon%3A "https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F6%2F67%2FMcGraw-Hill_Education_wordmark.svg%2F1024px-McGraw-Hill_Education_wordmark.svg.png"%2C%0A    pageTitle%3A "McGraw-Hill"%0A  %7D%2C%0A  %7B%0A    title%3A "Savvas Realize preset"%2C%0A    favicon%3A "https%3A%2F%2Fmi02209034.schoolwires.net%2Fcms%2Flib%2FMI02209034%2FCentricity%2FDomain%2F249%2Fsavvas_realize.png"%2C%0A    pageTitle%3A "Savvas Realize"%0A  %7D%2C%0A  %7B%0A    title%3A "IXL preset"%2C%0A    favicon%3A "https%3A%2F%2Fblog.ixl.com%2Fwp-content%2Fuploads%2F2017%2F05%2FIXL-Tw-profile.png"%2C%0A    pageTitle%3A "IXL"%0A  %7D%0A%5D%3B%0A%0A%2F%2F Create GUI%0Aconst guiDiv %3D document.createElement("div")%3B%0AguiDiv.style.position %3D "fixed"%3B%0AguiDiv.style.bottom %3D "20px"%3B%0AguiDiv.style.right %3D "20px"%3B%0AguiDiv.style.backgroundColor %3D "rgba(255%2C 255%2C 255%2C 0.3)"%3B%0AguiDiv.style.border %3D "1px solid %23ccc"%3B%0AguiDiv.style.borderRadius %3D "5px"%3B%0AguiDiv.style.padding %3D "10px"%3B%0AguiDiv.style.zIndex %3D "9999"%3B%0Adocument.body.appendChild(guiDiv)%3B%0A%0A%2F%2F Create GUI header%0Aconst headerDiv %3D document.createElement("div")%3B%0AheaderDiv.style.fontSize %3D "18px"%3B%0AheaderDiv.style.fontWeight %3D "bold"%3B%0AheaderDiv.style.marginBottom %3D "10px"%3B%0AheaderDiv.innerText %3D "TabMask"%3B%0AguiDiv.appendChild(headerDiv)%3B%0A%0A%2F%2F Create preset buttons%0Apresets.forEach((preset%2C index) %3D> %7B%0A  const presetButton %3D document.createElement("button")%3B%0A  presetButton.innerText %3D %60%24%7Bpreset.title%7D%60%3B%0A  presetButton.style.display %3D "block"%3B%0A  presetButton.style.marginBottom %3D "10px"%3B%0A  presetButton.style.cursor %3D "pointer"%3B%0A  presetButton.addEventListener("click"%2C () %3D> %7B%0A    %2F%2F Set favicon%0A    const faviconLink %3D document.querySelector("link%5Brel%3D'shortcut icon'%5D") %7C%7C document.createElement("link")%3B%0A    faviconLink.setAttribute("rel"%2C "shortcut icon")%3B%0A    faviconLink.setAttribute("href"%2C preset.favicon)%3B%0A    document.head.appendChild(faviconLink)%3B%0A    %0A    %2F%2F Set page title%0A    document.title %3D preset.pageTitle%3B%0A  %7D)%3B%0A  presetButton.addEventListener("mouseover"%2C () %3D> %7B%0A    presetButton.style.textDecoration %3D "underline"%3B%0A  %7D)%3B%0A  presetButton.addEventListener("mouseout"%2C () %3D> %7B%0A    presetButton.style.textDecoration %3D "none"%3B%0A  %7D)%3B%0A  guiDiv.appendChild(presetButton)%3B%0A%7D)%3B%0A%0A%2F%2F Create GUI footer%0Aconst footerDiv %3D document.createElement("div")%3B%0AfooterDiv.style.fontSize %3D "14px"%3B%0AfooterDiv.style.marginTop %3D "10px"%3B%0AfooterDiv.innerText %3D "Press E to hide%2Fshow menu."%3B%0AguiDiv.appendChild(footerDiv)%3B%0A%0A%2F%2F Add event listener for hiding%2Fshowing menu%0Adocument.addEventListener("keydown"%2C (event) %3D> %7B%0A  if (event.key %3D%3D%3D "e" %7C%7C event.key %3D%3D%3D "E") %7B%0A    guiDiv.style.display %3D guiDiv.style.display %3D%3D%3D "none" %3F "block" %3A "none"%3B%0A  %7D%0A%7D)%3B%7D)()%3B">TabMask</a>











