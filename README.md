<script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, doc, onSnapshot, setDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // 1. REMPLACE CECI PAR TES PROPRES INFOS FIREBASE (Trouvées dans ta console Firebase)
        const firebaseConfig = {
            apiKey: "TON_API_KEY",
            authDomain: "TON_PROJET.firebaseapp.com",
            projectId: "TON_PROJET_ID",
            storageBucket: "TON_PROJET.appspot.com",
            messagingSenderId: "TON_SENDER_ID",
            appId: "TON_APP_ID"
        };

        const app = initializeApp(firebaseConfig);
        const auth = getAuth(app);
        const db = getFirestore(app);
        const appId = 'cap-david-medical-v6';

        // ... (Le reste de ton code est correct jusqu'à l'export)

        // CORRECTION DE LA FIN DE LA FONCTION EXPORT
        window.exportData = () => {
            const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(appData, null, 2));
            const downloadAnchorNode = document.createElement('a');
            downloadAnchorNode.setAttribute("href", dataStr);
            downloadAnchorNode.setAttribute("download", `cap_david_backup_${new Date().toISOString().split('T')[0]}.json`);
            document.body.appendChild(downloadAnchorNode);
            downloadAnchorNode.click();
            downloadAnchorNode.remove(); // Correction ici
        };
    </script>
</body>
</html>
