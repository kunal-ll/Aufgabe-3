# Git-Workshop Aufgabe-3

**Aufgabe 3 - Branching und Merging Steckbrief**
Bitte clont das Projekt, navigiert in den Order rein und bearbeitet die folgende Aufgabe.
   ```sh
   git clone https://github.com/kunal-ll/Aufgabe-3.git
   cd Aufgabe-3
   ```

- Feature-Branch namens `feature-add-task` erstellen und hinwechseln 
- Aktualisiere `index.html` mit folgendem Skript und comitte dies:
     ```html
     <script>
         document.getElementById("add-task").addEventListener("click", function() {
             const taskText = document.getElementById("new-task").value;
             if (taskText) {
                 const li = document.createElement("li");
                 li.textContent = taskText;
                 const button = document.createElement("button");
                 button.textContent = "Done";
                 button.addEventListener("click", function() {
                     li.classList.toggle("done");
                 });
                 li.appendChild(button);
                 document.getElementById("tasks").appendChild(li);
                 document.getElementById("new-task").value = "";
             }
         });
     </script>
     ```
- Zurück zum `main` Branch wechseln
- Erstelle einen Branch namens `feature-delete-task`
- Aktualisiere `index.html` mit folgendem Skript und comitte dies:
     ```html
     <script>
         document.getElementById("add-task").addEventListener("click", function() {
             const taskText = document.getElementById("new-task").value;
             if (taskText) {
                 const li = document.createElement("li");
                 li.textContent = taskText;
                 const button = document.createElement("button");
                 button.textContent = "Delete";
                 button.addEventListener("click", function() {
                     li.remove();
                 });
                 li.appendChild(button);
                 document.getElementById("tasks").appendChild(li);
                 document.getElementById("new-task").value = "";
             }
         });
     </script>
     ```
- **Branch `feature-delete-task` in `main` mergen**
-  Commit-History ansehen:
      ```
      git log --oneline --all --graph
      ```
- **Branch `feature-add-task` auf `main` rebasen**
- Mergekonflikt beheben
- Commit-History nochmal ansehen
