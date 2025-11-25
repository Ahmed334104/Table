# Table
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مؤقت البومودورو الدراسي المتكامل</title>
    <style>
        :root {
            --primary: #3498db;
            --secondary: #2ecc71;
            --accent: #e74c3c;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --study-color: #e74c3c;
            --break-color: #2ecc71;
            --high-priority: #e74c3c;
            --medium-priority: #f39c12;
            --low-priority: #27ae60;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            color: white;
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 50px;
            padding: 5px;
            width: fit-content;
            margin-left: auto;
            margin-right: auto;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .tab {
            padding: 12px 30px;
            cursor: pointer;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .tab.active {
            background-color: var(--primary);
            color: white;
        }
        
        .tab-content {
            display: none;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* تصميم المؤقت */
        .timer-section {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .current-subject {
            font-size: 1.5rem;
            color: var(--dark);
            margin-bottom: 10px;
            font-weight: bold;
        }
        
        .timer-display {
            font-size: 5rem;
            font-weight: bold;
            margin: 20px 0;
            color: var(--dark);
            background-color: var(--light);
            border-radius: 15px;
            padding: 20px;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.1);
        }
        
        .session-info {
            font-size: 1.5rem;
            margin: 20px 0;
            color: var(--primary);
            font-weight: bold;
        }
        
        .progress-info {
            background: white;
            padding: 15px;
            border-radius: 10px;
            margin: 20px 0;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .progress-item {
            display: flex;
            justify-content: space-between;
            margin: 8px 0;
            padding: 5px 0;
            border-bottom: 1px solid #eee;
        }
        
        .controls {
            margin: 30px 0;
            text-align: center;
        }
        
        select, button {
            padding: 12px 20px;
            font-size: 1.1rem;
            border: none;
            border-radius: 10px;
            margin: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        select {
            background-color: var(--light);
            width: 200px;
        }
        
        button {
            background-color: var(--primary);
            color: white;
            font-weight: bold;
            min-width: 150px;
        }
        
        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        #startBtn {
            background-color: var(--secondary);
        }
        
        #pauseBtn {
            background-color: #f39c12;
        }
        
        #resetBtn {
            background-color: var(--accent);
        }
        
        /* تصميم الجدول الدراسي */
        .schedule-form {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-row {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .form-column {
            flex: 1;
            min-width: 200px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: var(--dark);
        }
        
        input, select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .total-hours-section {
            background: #e3f2fd;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
        }
        
        .schedule-list {
            margin-top: 20px;
        }
        
        .schedule-item {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 15px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
            border-left: 5px solid var(--primary);
            transition: all 0.3s ease;
        }
        
        .schedule-item.active {
            border-left-color: var(--secondary);
            box-shadow: 0 5px 15px rgba(46, 204, 113, 0.3);
        }
        
        .schedule-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .subject-name {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--dark);
        }
        
        .priority-badge {
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.9rem;
            color: white;
            font-weight: bold;
        }
        
        .priority-high { background: var(--high-priority); }
        .priority-medium { background: var(--medium-priority); }
        .priority-low { background: var(--low-priority); }
        
        .schedule-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .detail-item {
            display: flex;
            flex-direction: column;
        }
        
        .detail-label {
            font-size: 0.9rem;
            color: #666;
            margin-bottom: 5px;
        }
        
        .detail-value {
            font-weight: bold;
            color: var(--dark);
        }
        
        .progress-section {
            margin-top: 15px;
        }
        
        .progress-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
            font-size: 0.9rem;
        }
        
        .progress-bar {
            height: 8px;
            background: #f0f0f0;
            border-radius: 4px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: var(--primary);
            border-radius: 4px;
            transition: width 0.3s ease;
        }
        
        .schedule-actions {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }
        
        .action-btn {
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }
        
        .start-btn {
            background: var(--secondary);
            color: white;
        }
        
        .edit-btn {
            background: #f39c12;
            color: white;
        }
        
        .delete-btn {
            background: var(--accent);
            color: white;
        }
        
        .study-plan {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .plan-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .plan-title {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--dark);
        }
        
        .plan-summary {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .summary-item {
            text-align: center;
            padding: 15px;
            background: #f8f9fa;
            border-radius: 8px;
        }
        
        .summary-value {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .summary-label {
            font-size: 0.9rem;
            color: #666;
        }
        
        .pomodoro-sessions {
            margin-top: 20px;
        }
        
        .session-item {
            display: flex;
            align-items: center;
            padding: 10px;
            margin-bottom: 10px;
            background: #f8f9fa;
            border-radius: 8px;
            border-left: 4px solid var(--primary);
            transition: all 0.3s ease;
        }
        
        .session-item.active {
            background: #e8f5e8;
            border-left-color: var(--secondary);
        }
        
        .session-number {
            background: var(--primary);
            color: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            font-weight: bold;
        }
        
        .session-item.active .session-number {
            background: var(--secondary);
        }
        
        .session-info {
            flex: 1;
            font-size: 0.9rem;
        }
        
        .empty-schedule {
            text-align: center;
            padding: 40px;
            color: #666;
        }
        
        .empty-icon {
            font-size: 3rem;
            margin-bottom: 10px;
            opacity: 0.5;
        }
        
        .sound-notification {
            background-color: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 8px;
            padding: 10px;
            margin: 15px 0;
            text-align: center;
            color: #856404;
        }
        
        @media (max-width: 768px) {
            .timer-display {
                font-size: 3.5rem;
            }
            
            .tabs {
                flex-direction: column;
            }
            
            .tab {
                width: 100%;
            }
            
            .form-row {
                flex-direction: column;
            }
            
            .schedule-details {
                grid-template-columns: 1fr;
            }
            
            .plan-summary {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>مؤقت البومودورو الدراسي المتكامل</h1>
            <p>ادارة الوقت الدراسي بكفاءة مع نظام البومودورو</p>
        </header>
        
        <div class="tabs">
            <div class="tab active" data-tab="timer">⏰ المؤقت النشط</div>
            <div class="tab" data-tab="schedule">📚 الجدول الدراسي</div>
        </div>
        
        <!-- نافذة المؤقت -->
        <div id="timer" class="tab-content active">
            <div class="sound-notification">
                <strong>ملاحظة:</strong> قد تحتاج إلى النقر على أي مكان في الصفحة لتفعيل الأصوات أولاً.
            </div>
            
            <div class="timer-section">
                <div class="current-subject" id="currentSubject">المادة الحالية: لم يتم اختيار مادة</div>
                <div class="timer-display" id="display">25:00</div>
                <div class="session-info" id="sessionInfo">جلسة دراسة</div>
                
                <div class="progress-info">
                    <div class="progress-item">
                        <span>المادة:</span>
                        <span id="currentSubjectName">-</span>
                    </div>
                    <div class="progress-item">
                        <span>الجلسة:</span>
                        <span id="currentSession">0/0</span>
                    </div>
                    <div class="progress-item">
                        <span>التقدم الكلي:</span>
                        <span id="overallProgress">0%</span>
                    </div>
                    <div class="progress-item">
                        <span>الوقت المتبقي:</span>
                        <span id="remainingTime">-</span>
                    </div>
                </div>
            </div>
            
            <div class="controls">
                <button id="startBtn">▶ ابدأ</button>
                <button id="pauseBtn">⏸ إيقاف مؤقت</button>
                <button id="resetBtn">⏹ إعادة تعيين</button>
                <button id="nextSessionBtn" style="background: #9b59b6;">⏭ الجلسة التالية</button>
            </div>
        </div>
        
        <!-- نافذة الجدول الدراسي -->
        <div id="schedule" class="tab-content">
            <!-- نموذج إضافة مادة -->
            <div class="schedule-form">
                <h3>إضافة مادة جديدة</h3>
                <div class="form-row">
                    <div class="form-column">
                        <label for="subjectName">اسم المادة</label>
                        <input type="text" id="subjectName" placeholder="أدخل اسم المادة">
                    </div>
                    <div class="form-column">
                        <label for="priority">مستوى الصعوبة</label>
                        <select id="priority">
                            <option value="high">صعب 🔴</option>
                            <option value="medium" selected>متوسط 🟡</option>
                            <option value="low">سهل 🟢</option>
                        </select>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-column">
                        <label for="fileSize">حجم الملف (MB)</label>
                        <input type="number" id="fileSize" placeholder="حجم الملف بالميجابايت" min="1" value="10">
                    </div>
                    <div class="form-column">
                        <label for="importance">درجة الأهمية</label>
                        <select id="importance">
                            <option value="3">عالية جداً ⭐⭐⭐</option>
                            <option value="2" selected>متوسطة ⭐⭐</option>
                            <option value="1">منخفضة ⭐</option>
                        </select>
                    </div>
                </div>
                <button id="addSubjectBtn" class="action-btn start-btn" style="margin-top: 15px;">➕ إضافة المادة</button>
            </div>
            
            <!-- إجمالي الساعات -->
            <div class="total-hours-section">
                <div class="form-row">
                    <div class="form-column">
                        <label for="totalStudyHours">إجمالي ساعات الدراسة المطلوبة</label>
                        <input type="number" id="totalStudyHours" placeholder="عدد الساعات الإجمالي" min="1" value="4">
                    </div>
                    <div class="form-column">
                        <button id="distributeHoursBtn" class="action-btn start-btn" style="margin-top: 25px;">📊 توزيع الساعات تلقائياً</button>
                    </div>
                </div>
            </div>
            
            <!-- قائمة المواد -->
            <div class="schedule-list" id="scheduleList">
                <div class="empty-schedule">
                    <div class="empty-icon">📚</div>
                    <p>لا توجد مواد في جدولك الدراسي بعد</p>
                    <p>ابدأ بإضافة المواد الأولى باستخدام النموذج أعلاه</p>
                </div>
            </div>
            
            <!-- خطة الدراسة -->
            <div class="study-plan" id="studyPlan" style="display: none;">
                <div class="plan-header">
                    <div class="plan-title">📋 خطة الدراسة المقترحة</div>
                    <button id="startStudyPlanBtn" class="action-btn start-btn">🎯 بدء خطة الدراسة</button>
                </div>
                
                <div class="plan-summary">
                    <div class="summary-item">
                        <div class="summary-value" id="totalSubjects">0</div>
                        <div class="summary-label">عدد المواد</div>
                    </div>
                    <div class="summary-item">
                        <div class="summary-value" id="totalHours">0</div>
                        <div class="summary-label">إجمالي الساعات</div>
                    </div>
                    <div class="summary-item">
                        <div class="summary-value" id="totalSessions">0</div>
                        <div class="summary-label">جلسات البومودورو</div>
                    </div>
                    <div class="summary-item">
                        <div class="summary-value" id="completionTime">0</div>
                        <div class="summary-label">الوقت الإجمالي</div>
                    </div>
                </div>
                
                <div class="pomodoro-sessions" id="pomodoroSessions">
                    <!-- سيتم إضافة جلسات البومودورو هنا -->
                </div>
            </div>
        </div>
    </div>

    <script>
        // متغيرات التطبيق
        let subjects = [];
        let currentStudyPlan = [];
        let currentSessionIndex = 0;
        let currentSubjectIndex = 0;
        let timer;
        let isRunning = false;
        let isStudySession = true;
        let totalSeconds = 25 * 60;
        let sessionsCompleted = 0;
        let audioContext;
        let isAudioEnabled = false;

        // أوزان التوزيع حسب الصعوبة
        const difficultyWeights = {
            'high': 1.5,   // مواد صعبة تأخذ وقت أكثر
            'medium': 1.0, // مواد متوسطة
            'low': 0.7     // مواد سهلة تأخذ وقت أقل
        };

        // تهيئة الصفحة
        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
        });

        function initializeApp() {
            loadSubjects();
            setupEventListeners();
            document.body.addEventListener('click', enableAudio, { once: true });
            updateTimerDisplay();
        }

        function setupEventListeners() {
            // أحداث المؤقت
            document.getElementById('startBtn').addEventListener('click', startTimer);
            document.getElementById('pauseBtn').addEventListener('click', pauseTimer);
            document.getElementById('resetBtn').addEventListener('click', resetTimer);
            document.getElementById('nextSessionBtn').addEventListener('click', nextSession);

            // أحداث الجدول الدراسي
            document.getElementById('addSubjectBtn').addEventListener('click', addSubject);
            document.getElementById('distributeHoursBtn').addEventListener('click', distributeHours);
            document.getElementById('startStudyPlanBtn').addEventListener('click', startStudyPlan);

            // أحداث التبويب
            document.querySelectorAll('.tab').forEach(tab => {
                tab.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    switchTab(tabId);
                });
            });
        }

        // إدارة المواد الدراسية
        function addSubject() {
            const name = document.getElementById('subjectName').value.trim();
            const priority = document.getElementById('priority').value;
            const fileSize = parseInt(document.getElementById('fileSize').value);
            const importance = parseInt(document.getElementById('importance').value);

            if (!name || !fileSize) {
                alert('يرجى ملء جميع الحقول المطلوبة');
                return;
            }

            const subject = {
                id: Date.now(),
                name: name,
                priority: priority,
                fileSize: fileSize,
                importance: importance,
                assignedHours: 0,
                completed: 0,
                addedDate: new Date().toLocaleDateString('ar-EG')
            };

            subjects.push(subject);
            saveSubjects();
            renderSubjects();
            generateStudyPlan();

            alert(`تم إضافة المادة "${name}" بنجاح`);
            clearForm();
        }

        function clearForm() {
            document.getElementById('subjectName').value = '';
            document.getElementById('priority').value = 'medium';
            document.getElementById('fileSize').value = '10';
            document.getElementById('importance').value = '2';
        }

        // توزيع الساعات تلقائياً
        function distributeHours() {
            const totalHours = parseInt(document.getElementById('totalStudyHours').value);
            
            if (subjects.length === 0) {
                alert('يرجى إضافة مواد أولاً');
                return;
            }

            if (!totalHours || totalHours < 1) {
                alert('يرجى إدخال عدد ساعات صحيح');
                return;
            }

            // حساب الأوزان الإجمالية
            let totalWeight = 0;
            subjects.forEach(subject => {
                const difficultyWeight = difficultyWeights[subject.priority];
                const importanceWeight = subject.importance;
                totalWeight += difficultyWeight * importanceWeight;
            });

            // توزيع الساعات
            subjects.forEach(subject => {
                const difficultyWeight = difficultyWeights[subject.priority];
                const importanceWeight = subject.importance;
                const subjectWeight = difficultyWeight * importanceWeight;
                const assignedHours = (subjectWeight / totalWeight) * totalHours;
                
                subject.assignedHours = Math.round(assignedHours * 10) / 10; // تقريب لرقم عشري واحد
            });

            saveSubjects();
            renderSubjects();
            generateStudyPlan();

            alert(`تم توزيع ${totalHours} ساعة على ${subjects.length} مادة بنجاح`);
        }

        function renderSubjects() {
            const scheduleList = document.getElementById('scheduleList');
            
            if (subjects.length === 0) {
                scheduleList.innerHTML = `
                    <div class="empty-schedule">
                        <div class="empty-icon">📚</div>
                        <p>لا توجد مواد في جدولك الدراسي بعد</p>
                        <p>ابدأ بإضافة المواد الأولى باستخدام النموذج أعلاه</p>
                    </div>
                `;
                document.getElementById('studyPlan').style.display = 'none';
                return;
            }

            scheduleList.innerHTML = subjects.map(subject => `
                <div class="schedule-item ${currentSubjectIndex === subjects.findIndex(s => s.id === subject.id) && isRunning ? 'active' : ''}">
                    <div class="schedule-header">
                        <div class="subject-name">${subject.name}</div>
                        <div class="priority-badge priority-${subject.priority}">
                            ${subject.priority === 'high' ? 'صعب' : subject.priority === 'medium' ? 'متوسط' : 'سهل'}
                        </div>
                    </div>
                    
                    <div class="schedule-details">
                        <div class="detail-item">
                            <div class="detail-label">الساعات المخصصة</div>
                            <div class="detail-value">${subject.assignedHours} ساعة</div>
                        </div>
                        <div class="detail-item">
                            <div class="detail-label">الأهمية</div>
                            <div class="detail-value">${'⭐'.repeat(subject.importance)}</div>
                        </div>
                        <div class="detail-item">
                            <div class="detail-label">حجم الملف</div>
                            <div class="detail-value">${subject.fileSize} MB</div>
                        </div>
                        <div class="detail-item">
                            <div class="detail-label">تاريخ الإضافة</div>
                            <div class="detail-value">${subject.addedDate}</div>
                        </div>
                    </div>
                    
                    <div class="progress-section">
                        <div class="progress-info">
                            <span>التقدم</span>
                            <span>${subject.completed}%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: ${subject.completed}%"></div>
                        </div>
                    </div>
                    
                    <div class="schedule-actions">
                        <button class="action-btn start-btn" onclick="startSubjectStudy(${subject.id})">بدء الدراسة</button>
                        <button class="action-btn edit-btn" onclick="editSubject(${subject.id})">تعديل</button>
                        <button class="action-btn delete-btn" onclick="deleteSubject(${subject.id})">حذف</button>
                    </div>
                </div>
            `).join('');

            document.getElementById('studyPlan').style.display = 'block';
        }

        function generateStudyPlan() {
            if (subjects.length === 0) return;

            const totalHours = subjects.reduce((sum, subject) => sum + subject.assignedHours, 0);
            const totalSessions = Math.ceil(totalHours * 2); // كل ساعة = جلستين بومودورو
            const completionTime = totalHours + (totalSessions * 0.0833); // إضافة وقت الراحة

            document.getElementById('totalSubjects').textContent = subjects.length;
            document.getElementById('totalHours').textContent = totalHours.toFixed(1);
            document.getElementById('totalSessions').textContent = totalSessions;
            document.getElementById('completionTime').textContent = completionTime.toFixed(1);

            // توليد جلسات البومودورو
            currentStudyPlan = [];
            const sessionsContainer = document.getElementById('pomodoroSessions');
            sessionsContainer.innerHTML = '';

            let sessionNumber = 1;
            subjects.forEach(subject => {
                const subjectSessions = Math.ceil(subject.assignedHours * 2);
                
                for (let i = 0; i < subjectSessions; i++) {
                    const session = {
                        number: sessionNumber,
                        subject: subject.name,
                        subjectId: subject.id,
                        sessionInSubject: i + 1,
                        totalSessionsInSubject: subjectSessions
                    };
                    currentStudyPlan.push(session);

                    const sessionElement = document.createElement('div');
                    sessionElement.className = `session-item ${sessionNumber === currentSessionIndex + 1 && isRunning ? 'active' : ''}`;
                    sessionElement.innerHTML = `
                        <div class="session-number">${sessionNumber}</div>
                        <div class="session-info">
                            <strong>${subject.name}</strong> - جلسة ${i + 1} من ${subjectSessions}
                            <br><small>${subject.priority === 'high' ? '🔴 صعوبة عالية' : subject.priority === 'medium' ? '🟡 صعوبة متوسطة' : '🟢 صعوبة منخفضة'} - ${'⭐'.repeat(subject.importance)} أهمية</small>
                        </div>
                    `;
                    sessionsContainer.appendChild(sessionElement);
                    sessionNumber++;
                }
            });
        }

        function startSubjectStudy(subjectId) {
            const subjectIndex = subjects.findIndex(s => s.id === subjectId);
            if (subjectIndex !== -1) {
                currentSubjectIndex = subjectIndex;
                currentSessionIndex = 0;
                startStudyPlan();
                switchTab('timer');
            }
        }

        function startStudyPlan() {
            if (currentStudyPlan.length === 0) {
                alert('يرجى إنشاء خطة دراسة أولاً');
                return;
            }

            currentSessionIndex = 0;
            startTimer();
            updateCurrentSessionInfo();
        }

        function editSubject(subjectId) {
            const subject = subjects.find(s => s.id === subjectId);
            if (subject) {
                document.getElementById('subjectName').value = subject.name;
                document.getElementById('priority').value = subject.priority;
                document.getElementById('fileSize').value = subject.fileSize;
                document.getElementById('importance').value = subject.importance;
                
                deleteSubject(subjectId);
            }
        }

        function deleteSubject(subjectId) {
            subjects = subjects.filter(s => s.id !== subjectId);
            saveSubjects();
            renderSubjects();
            generateStudyPlan();
        }

        // إدارة المؤقت
        function startTimer() {
            if (!isRunning) {
                isRunning = true;
                timer = setInterval(updateTimer, 1000);
                document.getElementById('startBtn').textContent = '⏸ استئناف';
                updateCurrentSessionInfo();
            }
        }

        function pauseTimer() {
            if (isRunning) {
                isRunning = false;
                clearInterval(timer);
                document.getElementById('startBtn').textContent = '▶ استئناف';
            }
        }

        function resetTimer() {
            isRunning = false;
            clearInterval(timer);
            isStudySession = true;
            totalSeconds = 25 * 60;
            sessionsCompleted = 0;
            updateTimerDisplay();
            document.getElementById('sessionInfo').textContent = 'جلسة دراسة';
            document.getElementById('startBtn').textContent = '▶ ابدأ';
            updateCurrentSessionInfo();
        }

        function nextSession() {
            if (currentStudyPlan.length === 0) return;

            // تحديث تقدم المادة الحالية
            if (currentSessionIndex < currentStudyPlan.length) {
                const currentSession = currentStudyPlan[currentSessionIndex];
                const subject = subjects.find(s => s.id === currentSession.subjectId);
                if (subject) {
                    const sessionsPerSubject = Math.ceil(subject.assignedHours * 2);
                    const progressPerSession = 100 / sessionsPerSubject;
                    subject.completed = Math.min(100, subject.completed + progressPerSession);
                    saveSubjects();
                }
            }

            currentSessionIndex++;
            if (currentSessionIndex >= currentStudyPlan.length) {
                // انتهت جميع الجلسات
                alert('🎉 مبروك! لقد أكملت جميع جلسات الدراسة المخطط لها!');
                resetTimer();
                return;
            }

            // بدء الجلسة التالية
            isStudySession = true;
            totalSeconds = 25 * 60;
            updateTimerDisplay();
            updateCurrentSessionInfo();
            renderSubjects();
            generateStudyPlan();
        }

        function updateTimer() {
            if (totalSeconds > 0) {
                totalSeconds--;
                updateTimerDisplay();
            } else {
                // انتهت الجلسة
                playTone();
                if (isStudySession) {
                    // انتهت جلسة الدراسة
                    isStudySession = false;
                    totalSeconds = 5 * 60; // 5 دقائق راحة
                    document.getElementById('sessionInfo').textContent = '⏳ وقت راحة';
                    sessionsCompleted++;
                } else {
                    // انتهت جلسة الراحة
                    isStudySession = true;
                    totalSeconds = 25 * 60; // 25 دقيقة دراسة
                    document.getElementById('sessionInfo').textContent = '📚 جلسة دراسة';
                    nextSession();
                }
                updateTimerDisplay();
            }
        }

        function updateTimerDisplay() {
            const minutes = Math.floor(totalSeconds / 60);
            const seconds = totalSeconds % 60;
            document.getElementById('display').textContent = 
                `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }

        function updateCurrentSessionInfo() {
            if (currentStudyPlan.length === 0 || currentSessionIndex >= currentStudyPlan.length) {
                document.getElementById('currentSubject').textContent = 'المادة الحالية: لم يتم اختيار مادة';
                document.getElementById('currentSubjectName').textContent = '-';
                document.getElementById('currentSession').textContent = '0/0';
                document.getElementById('overallProgress').textContent = '0%';
                document.getElementById('remainingTime').textContent = '-';
                return;
            }

            const currentSession = currentStudyPlan[currentSessionIndex];
            const subject = subjects.find(s => s.id === currentSession.subjectId);
            
            if (subject) {
                document.getElementById('currentSubject').textContent = `المادة الحالية: ${subject.name}`;
                document.getElementById('currentSubjectName').textContent = subject.name;
                document.getElementById('currentSession').textContent = 
                    `${currentSession.sessionInSubject}/${currentSession.totalSessionsInSubject}`;
                
                // حساب التقدم الكلي
                const totalSessions = currentStudyPlan.length;
                const overallProgress = Math.round((currentSessionIndex / totalSessions) * 100);
                document.getElementById('overallProgress').textContent = `${overallProgress}%`;
                
                // حساب الوقت المتبقي
                const remainingSessions = totalSessions - currentSessionIndex;
                const remainingMinutes = remainingSessions * 30; // كل جلسة 30 دقيقة (25 دراسة + 5 راحة)
                const remainingHours = Math.floor(remainingMinutes / 60);
                const remainingMins = remainingMinutes % 60;
                document.getElementById('remainingTime').textContent = 
                    `${remainingHours} ساعة ${remainingMins} دقيقة`;
            }
        }

        function playTone() {
            // تنفيذ تشغيل النغمة
            if (isAudioEnabled && audioContext) {
                // كود تشغيل النغمة
            }
        }

        function enableAudio() {
            try {
                audioContext = new (window.AudioContext || window.webkitAudioContext)();
                isAudioEnabled = true;
            } catch (e) {
                console.error("خطأ في تفعيل الصوت:", e);
            }
        }

        // دوال التبويب
        function switchTab(tabId) {
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            
            document.querySelector(`.tab[data-tab="${tabId}"]`).classList.add('active');
            document.getElementById(tabId).classList.add('active');
        }

        // التخزين المحلي
        function saveSubjects() {
            localStorage.setItem('studySubjects', JSON.stringify(subjects));
        }

        function loadSubjects() {
            const saved = localStorage.getItem('studySubjects');
            if (saved) {
                subjects = JSON.parse(saved);
                renderSubjects();
                generateStudyPlan();
            }
        }
    </script>
</body>
</html>
