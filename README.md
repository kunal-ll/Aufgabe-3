# Git-Workshop Aufgabe-3

**Aufgabe 3 - Branching und Merging Steckbrief**
Bitte clont das Projekt, navigiert in den Order rein und bearbeitet die folgende Aufgabe.
   ```sh
   git clone https://github.com/kunal-ll/Aufgabe-3.git
   cd Aufgabe-3
   ```

- Feature-Branch namens `feature-done-task` erstellen und hinwechseln 
- Aktualisiere `index.html` mit folgendem Skript und comitte dies:
   ```html
   <script>
       document.getElementById("add-task").addEventListener("click", function() {
           const taskText = document.getElementById("new-task").value;
           if (taskText) {
               const li = document.createElement("li");
               li.textContent = taskText;
               // Create Done button
               const doneButton = document.createElement("button");
               doneButton.textContent = "Done";
               doneButton.addEventListener("click", function() {
                   li.classList.toggle("done");
               }); // done
               li.appendChild(doneButton);
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
// Create Delete button
               const deleteButton = document.createElement("button");
               deleteButton.textContent = "Delete";
               deleteButton.addEventListener("click", function() {
                   li.remove();
               }); // delete
               li.appendChild(deleteButton);
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
- **Branch `feature-done-task` auf `main` rebasen**
- Den Konflikt beheben
- Den rebase fortsetzen mit git rebase --continue
- Commit-History nochmal ansehen
