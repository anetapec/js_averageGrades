
# switch

  
const languageCode = "en";
        function greet() {
          switch (languageCode) {
            case "en":
              console.log("Hello!");
              break;
            case "es":
              console.log("¡Hola!");
              break;
            case "fr":
              console.log("Bonjour !");
              break;
            default:
              console.log("Unsupported language.");
          }
        }
        
    
greet();
