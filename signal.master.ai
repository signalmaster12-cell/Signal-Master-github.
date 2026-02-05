<div id="loginSection">
                <input type="text" id="passInput" placeholder="PASSWORD">
                <button class="btn-main" id="loginBtn">LOG IN</button>
            </div>

            <div id="adminPanel">
                <span class="admin-label">NAME</span>
                <input type="text" id="newName" placeholder="New Mod Name">
                <span class="admin-label">USER PASS</span>
                <input type="text" id="newPass" placeholder="User Password">
                <span class="admin-label">ADMIN PASS</span>
                <input type="text" id="newAdminPass" placeholder="Admin Password">
                <button class="btn-main" id="saveAdminBtn" style="background: #ff0000; color: #fff; margin-top: 5px;">SAVE</button>
            </div>

            <div id="signalSection" style="display:none;">
                <div class="signal-area">
                    <div id="signalResult" class="signal-text">READY</div>
                    <div style="font-size:9px; color:#ffff00; margin-top:2px;">NEXT: <span id="timerCount">30</span>S</div>
                </div>
            </div>

            <a href="https://t.me/fmtredrer58025" target="_blank" class="tg-button">
                <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg"> TELEGRAM
            </a>
            <button class="btn-admin-access" id="openAdminTrigger">ADMIN 11</button>

            <div class="action-row">
                <button class="btn-small btn-hide" id="hideBtn">HIDE</button>
                <button class="btn-small btn-exit" id="exitBtn">EXIT</button>
            </div>
        </div>
    </div>
</div>

<div id="floatingLogo"><img src="https://i.postimg.cc/XN5j7fZz/IMG-20260130-114558-595.jpg"></div>

<script>
    const firebaseConfig = {
        apiKey: "AIzaSyA9EmK-ptyAN__N9dPuZicRU7Q-W3waFo4",
        authDomain: "owner-jisan.firebaseapp.com",
        databaseURL: "https://owner-jisan-default-rtdb.firebaseio.com",
        projectId: "owner-jisan",
        storageBucket: "owner-jisan.firebasestorage.app",
        messagingSenderId: "610537281090",
        appId: "1:610537281090:android:f234b79622b97730093fdb"
    };
    firebase.initializeApp(firebaseConfig);
    const db = firebase.database();

    let currentPass = "HKPG88";
    let adminPass = "11";

    db.ref('settings').on('value', (snap) => {
        const val = snap.val();
        if(val) {
            if(val.name) document.getElementById("appTitle").innerText = val.name;
            if(val.pass) currentPass = val.pass;
            if(val.adminPass) adminPass = val.adminPass;
        }
    });

    document.getElementById("loginBtn").onclick = () => {
        const input = document.getElementById("passInput").value.trim();
        if(input === currentPass) {
            document.getElementById("loginSection").style.display = "none";
            document.getElementById("signalSection").style.display = "block";
            startSignals();
        } else {
            alert("WRONG PASSWORD!");
            window.location.href = "https://t.me/signal_master1";
        }
    };

    document.getElementById("openAdminTrigger").onclick = () => {
        let ask = prompt("ENTER ADMIN PASSWORD:");
        if(ask === adminPass) {
            document.getElementById("loginSection").style.display = "none";
            document.getElementById("signalSection").style.display = "none";
            document.getElementById("adminPanel").style.display = "block";
        } else {
            alert("ACCESS DENIED!");
        }
    };

    document.getElementById("saveAdminBtn").onclick = () => {
        const nName = document.getElementById("newName").value.trim();
        const nPass = document.getElementById("newPass").value.trim();
        const nAdmin = document.getElementById("newAdminPass").value.trim();
