<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام تقييم الفرضية - تابع لشرق الصحي</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #e0f7fa, #b2ebf2, #80deea);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .container {
            width: 100%;
            max-width: 900px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
            overflow: hidden;
            margin: 20px;
        }
        
        header {
            background: linear-gradient(90deg, #0288d1, #00bcd4);
            color: white;
            padding: 25px 30px;
            text-align: center;
            position: relative;
        }
        
        .logo-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 15px;
            gap: 15px;
        }
        
        .logo {
            background: white;
            border-radius: 50%;
            padding: 10px;
            width: 70px;
            height: 70px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .logo i {
            font-size: 2.5rem;
            color: #0288d1;
        }
        
        header h1 {
            font-size: 2.2rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }
        
        header p {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .form-container {
            padding: 30px;
        }
        
        .section-title {
            background: #0288d1;
            color: white;
            padding: 15px 20px;
            border-radius: 10px;
            margin: 30px 0 20px;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            position: relative;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            bottom: -10px;
            right: 20px;
            width: 0;
            height: 0;
            border-left: 10px solid transparent;
            border-right: 10px solid transparent;
            border-top: 10px solid #0288d1;
        }
        
        .section-title i {
            margin-left: 12px;
            font-size: 1.5rem;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-row {
            display: flex;
            flex-wrap: wrap;
            margin: 0 -10px;
        }
        
        .form-col {
            flex: 1;
            padding: 0 10px;
            min-width: 200px;
        }
        
        label {
            display: block;
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: #0288d1;
        }
        
        input, select, textarea {
            width: 100%;
            padding: 14px;
            border: 2px solid #e0f7fa;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
            background: #f5fdff;
        }
        
        input:focus, select:focus, textarea:focus {
            border-color: #0288d1;
            outline: none;
            box-shadow: 0 0 0 3px rgba(2, 136, 209, 0.2);
            background: white;
        }
        
        .time-input-group {
            display: flex;
            gap: 10px;
            align-items: center;
        }
        
        .time-input {
            flex: 1;
            display: flex;
            gap: 5px;
        }
        
        .time-input input {
            text-align: center;
            padding: 12px;
        }
        
        .time-period {
            width: 100px;
        }
        
        .time-separator {
            font-size: 1.2rem;
            font-weight: bold;
            color: #0288d1;
            padding: 0 5px;
        }
        
        .radio-group {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 8px;
        }
        
        .radio-option {
            display: flex;
            align-items: center;
            cursor: pointer;
            white-space: nowrap;
        }
        
        .radio-option input[type="radio"] {
            width: auto;
            margin-left: 8px;
        }
        
        .checkbox-group {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 8px;
        }
        
        .checkbox-option {
            display: flex;
            align-items: center;
            cursor: pointer;
            white-space: nowrap;
        }
        
        .checkbox-option input[type="checkbox"] {
            width: auto;
            margin-left: 8px;
        }
        
        .other-input {
            margin-top: 10px;
            display: none;
        }
        
        .other-input.show {
            display: block;
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        
        footer {
            text-align: center;
            padding: 20px;
            background: rgba(2, 136, 209, 0.05);
            font-size: 0.9rem;
            color: #555;
            border-top: 2px solid #e0f7fa;
        }
        
        .error-message {
            color: #d32f2f;
            font-size: 0.85rem;
            margin-top: 5px;
            display: none;
        }
        
        .error-input {
            border-color: #d32f2f !important;
            background: #ffebee !important;
        }
        
        /* تحسينات للقسم الجديد */
        .event-analysis-item {
            margin-bottom: 25px;
        }
        
        .event-analysis-item label i {
            margin-left: 8px;
            color: #0288d1;
        }
        
        .event-analysis-item textarea {
            min-height: 120px;
            resize: vertical;
        }
        
        /* تصميم قسم مؤشرات القياس الجديد */
        .measurement-item {
            background: #f8fdff;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            border: 1px solid #e0f7fa;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }
        
        .measurement-question {
            font-weight: 600;
            font-size: 1.1rem;
            margin-bottom: 15px;
            color: #0288d1;
            display: flex;
            align-items: center;
        }
        
        .measurement-question i {
            margin-left: 10px;
            font-size: 1.2rem;
        }
        
        .measurement-options {
            display: flex;
            gap: 20px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }
        
        .measurement-options label {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: normal;
            color: #555;
        }
        
        .measurement-notes {
            margin-top: 10px;
        }
        
        .measurement-notes textarea {
            min-height: 80px;
            resize: vertical;
        }
        
        /* قسم الأسئلة الخاصة بالرمز */
        .code-specific-section {
            display: none;
            background: #f0f9ff;
            border-radius: 15px;
            padding: 25px;
            margin-top: 30px;
            border: 2px solid #0288d1;
            box-shadow: 0 5px 15px rgba(2, 136, 209, 0.1);
        }
        
        .code-specific-section.show {
            display: block;
            animation: slideIn 0.5s ease;
        }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .code-specific-item {
            background: white;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            border: 1px solid #e0f7fa;
            box-shadow: 0 3px 8px rgba(0,0,0,0.05);
        }
        
        .code-title {
            background: #ff5252;
            color: white;
            padding: 12px 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
            font-size: 1.4rem;
        }
        
        
        @media (max-width: 768px) {
            .form-col {
                flex: 0 0 100%;
                margin-bottom: 15px;
            }
            
            .time-input-group {
                flex-direction: column;
                gap: 5px;
            }
            
            .time-input {
                width: 100%;
            }
            
            header h1 {
                font-size: 1.8rem;
            }
            
            .radio-group, .checkbox-group {
                flex-direction: column;
                gap: 10px;
            }
            
            .measurement-options {
                flex-direction: column;
                gap: 10px;
            }
            
            .submit-btn {
                width: 100%;
                padding: 16px;
            }
        }
        
        /* تحسينات للتقدم */
        .progress-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: #e0f7fa;
            z-index: 1000;
        }
        
        .progress-bar {
            height: 100%;
            background: #0288d1;
            width: 0%;
            transition: width 0.3s ease;
        }
        
        .scroll-top-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 50px;
            height: 50px;
            background: #0288d1;
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 3px 10px rgba(0,0,0,0.2);
            opacity: 0;
            transition: opacity 0.3s;
            z-index: 999;
        }
        
        .scroll-top-btn.visible {
            opacity: 1;
        }
                /* ألوان مخصصة حسب نوع الرمز */
        .pink-theme .code-title {
            background-color: #f06292; /* وردي */
        }

        .silver-theme .code-title {
            background-color: #b0bec5; /* فضي */
            color: black;
        }

        .yellow-theme .code-title {
            background-color: #fdd835; /* أصفر */
            color: black;
        }

        .gray-theme .code-title {
            background-color: #9e9e9e;
            color: white;
        }

        .black-theme .code-title {
            background-color: #212121;
            color: white;
        }

        .orange-theme .code-title {
            background-color: #ff9800;
            color: white;
        }

        .brown-theme .code-title {
            background-color: #8d6e63;
            color: white;
        }

        .red-theme .code-title {
            background-color: #ff5252;
            color: white;
        }
        .btn-container {
            text-align: center;
            margin-top: 40px;
        }
        
        .submit-btn {
            background: linear-gradient(90deg, #0288d1, #00bcd4);
            color: white;
            border: none;
            padding: 16px 50px;
            font-size: 1.2rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(2, 136, 209, 0.3);
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }
        
        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(2, 136, 209, 0.4);
            background: linear-gradient(90deg, #00bcd4, #0288d1);
        }
        
        .submit-btn:active {
            transform: translateY(1px);
        }

    </style>
</head>
<body>
    <div class="progress-container">
        <div class="progress-bar" id="progressBar"></div>
    </div>
    
    <div class="scroll-top-btn" id="scrollTopBtn">
        <i class="fas fa-arrow-up"></i>
    </div>
    
    <div class="container">
        <header>
            <div class="logo-container">
                <div class="logo">
                    <i class="fas fa-hospital"></i>
                </div>
                <div>
                    <h1><i class="fas fa-clipboard-check"></i> نظام تقييم الفرضية</h1>
                    <p>تابع لتجمع الشرقية الصحي</p>
                </div>
            </div>
        </header>
        
        <div class="form-container">
            <form id="surveyForm">
                <!-- قسم بيانات الفرضية (الأول) -->
                <div class="section-title">
                    <i class="fas fa-database"></i> بيانات الفرضية
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label for="year"><i class="fas fa-calendar-alt"></i> السنة</label>
                            <input type="number" id="year" name="year" required min="2000" max="2100" placeholder="2023">
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label for="month"><i class="fas fa-calendar"></i> الشهر</label>
                            <input type="number" id="month" name="month" required min="1" max="12" placeholder="12">
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label for="day"><i class="fas fa-calendar-day"></i> اليوم</label>
                            <input type="number" id="day" name="day" required min="1" max="31" placeholder="25">
                        </div>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label for="weekday"><i class="fas fa-calendar-week"></i> يوم الأسبوع</label>
                            <select id="weekday" name="weekday" required>
                                <option value="" disabled selected>اختر يوم الأسبوع</option>
                                <option value="السبت">السبت</option>
                                <option value="الأحد">الأحد</option>
                                <option value="الاثنين">الاثنين</option>
                                <option value="الثلاثاء">الثلاثاء</option>
                                <option value="الأربعاء">الأربعاء</option>
                                <option value="الخميس">الخميس</option>
                                <option value="الجمعة">الجمعة</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label for="establishment"><i class="fas fa-building"></i> اسم المنشأة</label>
                            <input type="text" id="establishment" name="establishment" required placeholder="أدخل اسم المنشأة">
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label for="evaluator"><i class="fas fa-user-tie"></i> اسم المقيم</label>
                            <input type="text" id="evaluator" name="evaluator" required placeholder="أدخل اسم المقيم">
                        </div>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label for="specialty"><i class="fas fa-graduation-cap"></i> التخصص</label>
                            <input type="text" id="specialty" name="specialty" required placeholder="أدخل التخصص">
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label for="codeType"><i class="fas fa-code"></i> نوع الرمز</label>
                            <select id="codeType" name="codeType" required>
                                <option value="" disabled selected>اختر نوع الرمز</option>
                                <option value="الرمز الاحمر">الرمز الاحمر</option>
                                <option value="الرمز الابيض">الرمز الابيض</option>
                                <option value="الرمز الفضي">الرمز الفضي</option>
                                <option value="الرمز الوردي">الرمز الوردي</option>
                                <option value="الرمز الاسود">الرمز الاسود</option>
                                <option value="الرمز البرتقالي">الرمز البرتقالي</option>
                                <option value="الرمز البني">الرمز البني</option>
                                <option value="الرمز الرمادي">الرمز الرمادي</option>
                                <option value="الرمز الاصفر">الرمز الاصفر</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <!-- قسم البيانات الأولية (الثاني) -->
                <div class="section-title">
                    <i class="fas fa-layer-group"></i> البيانات الأولية
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label for="trainingType"><i class="fas fa-chalkboard-teacher"></i> نوع التدريب</label>
                            <div class="radio-group">
                                <label class="radio-option">
                                    <input type="radio" name="trainingType" value="تدريب طاولة" required>
                                    تدريب طاولة
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="trainingType" value="فرضية" required>
                                    فرضية
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="trainingType" value="أخرى" id="otherTraining" required>
                                    أخرى
                                </label>
                            </div>
                            <div class="other-input" id="otherTrainingInput">
                                <input type="text" id="otherTrainingText" name="otherTrainingText" placeholder="يرجى تحديد نوع التدريب">
                            </div>
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label for="eventType"><i class="fas fa-calendar-check"></i> نوع الحدث</label>
                            <div class="radio-group">
                                <label class="radio-option">
                                    <input type="radio" name="eventType" value="داخلية" required>
                                    داخلية
                                </label>
                                <label class="radio-option">
                                    <input type="radio" name="eventType" value="خارجية" required>
                                    خارجية
                                </label>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="trainingGoals"><i class="fas fa-bullseye"></i> الأهداف من التدريب</label>
                    <textarea id="trainingGoals" name="trainingGoals" rows="3" placeholder="حدد الأهداف الرئيسية من هذا التدريب"></textarea>
                </div>
                
                <!-- قسم تسجيل الوقت (الثالث) -->
                <div class="section-title">
                    <i class="fas fa-stopwatch"></i> تسجيل الوقت
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label><i class="fas fa-play-circle"></i> وقت بدء الفرضية المخطط</label>
                            <div class="time-input-group">
                                <div class="time-input">
                                    <input type="number" id="plannedStartHour" name="plannedStartHour" min="1" max="12" placeholder="ساعة" required>
                                    <span class="time-separator">:</span>
                                    <input type="number" id="plannedStartMinute" name="plannedStartMinute" min="0" max="59" placeholder="دقيقة" required>
                                    <select class="time-period" id="plannedStartPeriod" name="plannedStartPeriod" required>
                                        <option value="صباح">صباح</option>
                                        <option value="مساء">مساء</option>
                                    </select>
                                </div>
                            </div>
                            <div class="error-message" id="plannedStartHourError">يجب أن تكون الساعة بين 1 و 12</div>
                            <div class="error-message" id="plannedStartMinuteError">يجب أن تكون الدقيقة بين 0 و 59</div>
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label><i class="fas fa-play-circle"></i> وقت بدء الفرضية الفعلي</label>
                            <div class="time-input-group">
                                <div class="time-input">
                                    <input type="number" id="actualStartHour" name="actualStartHour" min="1" max="12" placeholder="ساعة" required>
                                    <span class="time-separator">:</span>
                                    <input type="number" id="actualStartMinute" name="actualStartMinute" min="0" max="59" placeholder="دقيقة" required>
                                    <select class="time-period" id="actualStartPeriod" name="actualStartPeriod" required>
                                        <option value="صباح">صباح</option>
                                        <option value="مساء">مساء</option>
                                    </select>
                                </div>
                            </div>
                            <div class="error-message" id="actualStartHourError">يجب أن تكون الساعة بين 1 و 12</div>
                            <div class="error-message" id="actualStartMinuteError">يجب أن تكون الدقيقة بين 0 و 59</div>
                        </div>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-col">
                        <div class="form-group">
                            <label><i class="fas fa-phone-alt"></i> وقت التواصل مع مركز التحكم بالموارد</label>
                            <div class="time-input-group">
                                <div class="time-input">
                                    <input type="number" id="contactHour" name="contactHour" min="1" max="12" placeholder="ساعة" required>
                                    <span class="time-separator">:</span>
                                    <input type="number" id="contactMinute" name="contactMinute" min="0" max="59" placeholder="دقيقة" required>
                                    <select class="time-period" id="contactPeriod" name="contactPeriod" required>
                                        <option value="صباح">صباح</option>
                                        <option value="مساء">مساء</option>
                                    </select>
                                </div>
                            </div>
                            <div class="error-message" id="contactHourError">يجب أن تكون الساعة بين 1 و 12</div>
                            <div class="error-message" id="contactMinuteError">يجب أن تكون الدقيقة بين 0 و 59</div>
                        </div>
                    </div>
                    
                    <div class="form-col">
                        <div class="form-group">
                            <label><i class="fas fa-stop-circle"></i> وقت انتهاء الفرضية</label>
                            <div class="time-input-group">
                                <div class="time-input">
                                    <input type="number" id="endHour" name="endHour" min="1" max="12" placeholder="ساعة" required>
                                    <span class="time-separator">:</span>
                                    <input type="number" id="endMinute" name="endMinute" min="0" max="59" placeholder="دقيقة" required>
                                    <select class="time-period" id="endPeriod" name="endPeriod" required>
                                        <option value="صباح">صباح</option>
                                        <option value="مساء">مساء</option>
                                    </select>
                                </div>
                            </div>
                            <div class="error-message" id="endHourError">يجب أن تكون الساعة بين 1 و 12</div>
                            <div class="error-message" id="endMinuteError">يجب أن تكون الدقيقة بين 0 و 59</div>
                        </div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="timeNotes"><i class="fas fa-sticky-note"></i> ملاحظات حول التوقيت</label>
                    <textarea id="timeNotes" name="timeNotes" rows="3" placeholder="أي ملاحظات حول التوقيت أو التنفيذ"></textarea>
                </div>
                
                <!-- قسم HEPPU and Incident command (الرابع) -->
                <div class="section-title">
                    <i class="fas fa-headset"></i> HEPPU and Incident command
                </div>
                
                <div class="form-group">
                    <label><i class="fas fa-toggle-on"></i> تم تفعيل وحدة التخطيط والاستعداد</label>
                    <div class="radio-group">
                        <label class="radio-option">
                            <input type="radio" name="heppuActivated" value="نعم" required>
                            نعم
                        </label>
                        <label class="radio-option">
                            <input type="radio" name="heppuActivated" value="لا" required>
                            لا
                        </label>
                    </div>
                </div>
                
                <div class="form-group">
                    <label><i class="fas fa-comments"></i> هل كان التواصل فعال</label>
                    <div class="radio-group">
                        <label class="radio-option">
                            <input type="radio" name="effectiveCommunication" value="نعم" required>
                            نعم
                        </label>
                        <label class="radio-option">
                            <input type="radio" name="effectiveCommunication" value="لا" required>
                            لا
                        </label>
                    </div>
                </div>
                
                <div class="form-group">
                    <label><i class="fas fa-broadcast-tower"></i> طريقة التواصل</label>
                    <div class="checkbox-group">
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="راديو">
                            راديو
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="برافو">
                            برافو
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="جوال">
                            جوال
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="خط ارضي">
                            خط ارضي
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="ايميل">
                            ايميل
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="خط ساخن">
                            خط ساخن
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="communicationMethod" value="أخرى" id="otherCommunicationMethod">
                            أخرى
                        </label>
                    </div>
                    <div class="other-input" id="otherCommunicationMethodInput">
                        <input type="text" id="otherCommunicationMethodText" name="otherCommunicationMethodText" placeholder="يرجى تحديد طريقة التواصل">
                    </div>
                </div>
                
                <div class="form-group">
                    <label><i class="fas fa-clipboard-list"></i> طريقة تسجيل المعلومات والتحديثات الخاصة بالحدث</label>
                    <div class="checkbox-group">
                        <label class="checkbox-option">
                            <input type="checkbox" name="infoRecordingMethod" value="الكترونية">
                            الكترونية
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="infoRecordingMethod" value="ورق ملاحظات">
                            ورق ملاحظات
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="infoRecordingMethod" value="سبورة بيضاء">
                            سبورة بيضاء
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="infoRecordingMethod" value="لم يتم التسجيل">
                            لم يتم التسجيل
                        </label>
                        <label class="checkbox-option">
                            <input type="checkbox" name="infoRecordingMethod" value="أخرى" id="otherRecordingMethod">
                            أخرى
                        </label>
                    </div>
                    <div class="other-input" id="otherRecordingMethodInput">
                        <input type="text" id="otherRecordingMethodText" name="otherRecordingMethodText" placeholder="يرجى تحديد طريقة التسجيل">
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="heppuNotes"><i class="fas fa-sticky-note"></i> ملاحظات</label>
                    <textarea id="heppuNotes" name="heppuNotes" rows="3" placeholder="أي ملاحظات إضافية"></textarea>
                </div>
                
                <!-- قسم تحليل الحدث (الخامس) -->
                <div class="section-title">
                    <i class="fas fa-chart-bar"></i> تحليل الحدث
                </div>
                
                <div class="form-group">
                    <div class="event-analysis-item">
                        <label for="eventDescription"><i class="fas fa-clipboard-list"></i> الحدث</label>
                        <textarea id="eventDescription" name="eventDescription" rows="4" placeholder="صِف الحدث بشكل تفصيلي، بما في ذلك الظروف والأسباب والنتائج" required></textarea>
                    </div>
                    
                    <div class="event-analysis-item">
                        <label for="strengths"><i class="fas fa-thumbs-up"></i> نقاط القوة</label>
                        <textarea id="strengths" name="strengths" rows="4" placeholder="ما هي نقاط القوة التي تمت ملاحظتها خلال الحدث؟" required></textarea>
                    </div>
                    
                    <div class="event-analysis-item">
                        <label for="improvements"><i class="fas fa-tools"></i> مناطق التحسين</label>
                        <textarea id="improvements" name="improvements" rows="4" placeholder="ما هي المجالات التي تحتاج إلى تحسين؟" required></textarea>
                    </div>
                    
                    <div class="event-analysis-item">
                        <label for="recommendations"><i class="fas fa-lightbulb"></i> التوصيات</label>
                        <textarea id="recommendations" name="recommendations" rows="4" placeholder="ما هي التوصيات المقدمة بناءً على هذا التحليل؟" required></textarea>
                    </div>
                    
                    <div class="event-analysis-item">
                        <label for="analystName"><i class="fas fa-signature"></i> الاسم</label>
                        <input type="text" id="analystName" name="analystName" placeholder="اسم المحلل" required>
                    </div>
                </div>
                
                <div class="section-title">
                    <i class="fas fa-chart-bar"></i> مؤشر قياس الفرضيات
                </div>
                
                <!-- اختيار نوع الرمز في القسم السادس -->
                <div class="form-group">
                    <label for="section6CodeType"><i class="fas fa-code"></i> نوع الرمز</label>
                    <select id="section6CodeType" name="section6CodeType" required>
                      <option value="" disabled selected>اختر نوع الرمز</option>
                      <option value="الرمز الاحمر">الرمز الأحمر</option>
                      <option value="الرمز الفضي/الابيض">الرمز الفضي/الابيض</option> 
                      <option value="الرمز الوردي">الرمز الوردي</option>
                      <option value="الرمز الاسود">الرمز الاسود</option>
                      <option value="الرمز البرتقالي">الرمز البرتقالي</option>
                      <option value="الرمز البني">الرمز البني</option>
                      <option value="الرمز الرمادي">الرمز الرمادي</option>
                      <option value="الرمز الاصفر (اصابات متعددة)">الرمز الاصفر(اصابات متعددة)</option>
                      <option value="الرمز الاصفر (امراض معدية)">الرمز الاصفر(امراض معدية)</option>
                    </select>
                </div>
                
                <!-- القسم العام لمؤشرات القياس -->
                <div id="generalMeasurementSection">
                    <!-- البند الأول -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-user-tie"></i> 
                            تعيين قائد يقوم بادارة الحدث وتوزيع المهام على المشاركين بالفرضية
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="leaderAppointed" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="leaderAppointed" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="leaderNotes" placeholder="ملاحظات حول تعيين القائد وتوزيع المهام"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الثاني -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-bullhorn"></i> 
                            اتباع الية البلاغ الصحيحة
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="notificationProcedure" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="notificationProcedure" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="notificationNotes" placeholder="ملاحظات حول الية البلاغ"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الثالث -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-hospital-alt"></i> 
                            جاهزية المستشفى لحالات الطوارئ "البنية التحتية"
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="hospitalReadiness" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="hospitalReadiness" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="readinessNotes" placeholder="ملاحظات حول جاهزية البنية التحتية"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الرابع -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-comments"></i> 
                            التواصل مع الجهات الخارجية والتحديث المستمر معهم
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="externalCommunication" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="externalCommunication" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="communicationNotes" placeholder="ملاحظات حول التواصل مع الجهات الخارجية"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الخامس -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-tags"></i> 
                            وجود منطقة الفرز (الأولية، الثانوية) للحالات الموضحة بالألوان
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="triageArea" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="triageArea" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="triageNotes" placeholder="ملاحظات حول مناطق الفرز"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند السادس -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-id-card"></i> 
                            استخدام بطاقات الفرز لتصنيف الحالات بشكل صحيح
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="triageCards" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="triageCards" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="cardsNotes" placeholder="ملاحظات حول استخدام بطاقات الفرز"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند السابع -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-user-shield"></i> 
                            التزام الطاقم الطبي بارتداء معدات الوقاية الشخصية (PPE)
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="ppeCompliance" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="ppeCompliance" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="ppeNotes" placeholder="ملاحظات حول ارتداء معدات الوقاية"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الثامن -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-users"></i> 
                            حضور فريق الاستجابة السريعة (IRT)
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="irtPresence" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="irtPresence" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="irtNotes" placeholder="ملاحظات حول فريق الاستجابة السريعة"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند التاسع -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-user-shield"></i> 
                            ارشاد وتوجيه المراجعين وتنظيم الدخول وخروج الاسعاف من قبل الامن
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="securityManagement" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="securityManagement" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="securityNotes" placeholder="ملاحظات حول دور الأمن في تنظيم الدخول والخروج"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند العاشر -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-route"></i> 
                            تامين ممرات والمصاعد عند نقل المرضى
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="safePathways" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="safePathways" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="pathwaysNotes" placeholder="ملاحظات حول تأمين الممرات والمصاعد"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الحادي عشر -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-ambulance"></i> 
                            تواجد سيارات الاسعاف والتنسيق معهم عند الحاجة لنقل الحالات الى منشاة اخرى
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="ambulanceCoordination" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="ambulanceCoordination" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="ambulanceNotes" placeholder="ملاحظات حول سيارات الإسعاف والتنسيق"></textarea>
                        </div>
                    </div>
                    
                    <!-- البند الثاني عشر -->
                    <div class="measurement-item">
                        <div class="measurement-question">
                            <i class="fas fa-map-marker-alt"></i> 
                            توافر نقاط تجمع بالمنشاه
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="gatheringPoints" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="gatheringPoints" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="gatheringNotes" placeholder="ملاحظات حول نقاط التجمع"></textarea>
                        </div>
                    </div>
                </div>
                
                <!-- قسم الأسئلة الخاصة بالرمز الأحمر -->
                <div class="code-specific-section" id="redCodeSection">
                    <div class="code-title">
                        <i class="fas fa-fire"></i> تقييم رمز الاحمر
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-fire-extinguisher"></i> 
                            استخدام طفايات الحريق اليدوية (PASS+RACE)
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="fireExtinguisher" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="fireExtinguisher" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="fireExtinguisherNotes" placeholder="ملاحظات حول استخدام طفايات الحريق"></textarea>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-door-open"></i> 
                            وضع علامة على الابواب بعد الاخلاء الغرفة / المكتب / القسم
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="doorMarking" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="doorMarking" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-tools"></i> 
                            وجود ادوات مكافحة الحريق
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="fireTools" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="fireTools" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="fireToolsNotes" placeholder="ملاحظات حول أدوات مكافحة الحريق"></textarea>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-bell"></i> 
                            وجود اجهزة انذار الحريق
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="fireAlarm" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="fireAlarm" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-exit"></i> 
                            وجود مخارج ابواب البطوارئ
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="emergencyExits" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="emergencyExits" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-walking"></i> 
                            خلو كافة مسالك الهروب من العوائق
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="escapeRoutes" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="escapeRoutes" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-sign"></i> 
                            وجود لوحات ارشادية التي تسهل من عمليات الاخلاء
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="signage" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="signage" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="signageNotes" placeholder="ملاحظات حول اللوحات الإرشادية"></textarea>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-wind"></i> 
                            اغلاق مصادر تيار الهواء (النوافذ,المكيفات , الشفاطات الهوائية)
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="airSources" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="airSources" value="لا" required> لا
                            </label>
                        </div>
                        <div class="measurement-notes">
                            <textarea name="airSourcesNotes" placeholder="ملاحظات حول مصادر الهواء"></textarea>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-plug"></i> 
                            اغلاق مصدر التيار الكهربائي
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="powerOff" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="powerOff" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-door-closed"></i> 
                            وجود ابواب مقاومة للنار
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="fireDoors" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="fireDoors" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-fan"></i> 
                            مجرى المكيفات مزود ب لسان عازل عن الدخان
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="acSmokeDamper" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="acSmokeDamper" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-tint"></i> 
                            وضع قطعة قماش مبللة تحت الابواب
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="wetCloth" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="wetCloth" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-volume-up"></i> 
                            صوت السماعات في الاقسام والممرات مسموع بشكل واضح
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="speakersAudible" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="speakersAudible" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-lightbulb"></i> 
                            مخرج الطوارئ مضاء
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="exitLight" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="exitLight" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-map-marker-alt"></i> 
                            مخرج الطوارئ مزود برقم الطابق
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="exitFloorNumber" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="exitFloorNumber" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-elevator"></i> 
                            منع استخدام المصاعد
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="elevatorBan" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="elevatorBan" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-user-slash"></i> 
                            منع دخول الغير معنيين بالحدث
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="unauthorizedBan" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="unauthorizedBan" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                    
                    <div class="code-specific-item">
                        <div class="measurement-question">
                            <i class="fas fa-camera"></i> 
                            منع التجمهر والتصوير
                        </div>
                        <div class="measurement-options">
                            <label>
                                <input type="radio" name="crowdControl" value="نعم" required> نعم
                            </label>
                            <label>
                                <input type="radio" name="crowdControl" value="لا" required> لا
                            </label>
                        </div>
                    </div>
                </div>
                
                        <!-- قسم الرمز الوردي -->
                <div class="code-specific-section pink-theme" id="pinkCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز الوردي</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز الفضي/الابيض -->
                <div class="code-specific-section silver-theme" id="silverWhiteCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز الفضي/الابيض</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز الاصفر (اصابات متعددة) -->
                <div class="code-specific-section yellow-theme" id="yellowInjuryCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز الأصفر (إصابات متعددة)</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز الاصفر (امراض معدية) -->
                <div class="code-specific-section yellow-theme" id="yellowInfectionCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز الأصفر (ألامراض معدية)</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز الرمادي -->
                <div class="code-specific-section gray-theme" id="grayCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز الرمادي</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز الاسود -->
                <div class="code-specific-section black-theme" id="blackCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز الأسود</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز البرتقالي -->
                <div class="code-specific-section orange-theme" id="orangeCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز البرتقالي</div>
                    <!-- أضف أسئلتك هنا -->
                </div>

                <!-- قسم الرمز البني -->
                <div class="code-specific-section brown-theme" id="brownCodeSection">
                    <div class="code-title"><i class="fas fa-tasks"></i> تقييم رمز البني</div>
                    <!-- أضف أسئلتك هنا -->
                </div>
                <div class="btn-container">
                    <button type="submit" class="submit-btn">
                        <i class="fas fa-paper-plane"></i> إرسال التقييم
                    </button>
                </div>
            </form>
        </div>

        
        <footer>
            <p>© 2025 نظام تقييم الفرضية - تابع لتجمع الشرقية الصحي</p>
            <p> جميع الحقوق محفوظة - تم التطوير بواسطة سعاد مرزا</p>
        </footer>
    </div>

    <script>
        // تعيين التاريخ الحالي تلقائياً
        function setCurrentDate() {
            const now = new Date();
            document.getElementById('year').value = now.getFullYear();
            document.getElementById('month').value = now.getMonth() + 1;
            document.getElementById('day').value = now.getDate();
            
            // تعيين يوم الأسبوع
            const weekdays = ['الأحد', 'الاثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت'];
            document.getElementById('weekday').value = weekdays[now.getDay()];
        }
        
        // إظهار/إخفاء حقل "أخرى" عند تغيير اختيار نوع التدريب
        const trainingTypeRadios = document.querySelectorAll('input[name="trainingType"]');
        trainingTypeRadios.forEach(radio => {
            radio.addEventListener('change', function() {
                const otherInput = document.getElementById('otherTrainingInput');
                if (this.id === 'otherTraining' && this.checked) {
                    otherInput.classList.add('show');
                } else {
                    otherInput.classList.remove('show');
                }
            });
        });
        
        // إظهار/إخفاء حقل "أخرى" لطريقة التواصل
        document.getElementById('otherCommunicationMethod').addEventListener('change', function() {
            const otherInput = document.getElementById('otherCommunicationMethodInput');
            if (this.checked) {
                otherInput.classList.add('show');
            } else {
                otherInput.classList.remove('show');
            }
        });
        
        // إظهار/إخفاء حقل "أخرى" لطريقة التسجيل
        document.getElementById('otherRecordingMethod').addEventListener('change', function() {
            const otherInput = document.getElementById('otherRecordingMethodInput');
            if (this.checked) {
                otherInput.classList.add('show');
            } else {
                otherInput.classList.remove('show');
            }
        });
        
        // التحقق من صحة الوقت
        function validateTime(input, isHour = true) {
            const value = parseInt(input.value);
            const errorId = input.id + 'Error';
            const errorElement = document.getElementById(errorId);
            
            if (isNaN(value)) {
                input.classList.add('error-input');
                errorElement.style.display = 'block';
                errorElement.textContent = 'يجب إدخال رقم صحيح';
                return false;
            }
            
            if (isHour) {
                if (value < 1 || value > 12) {
                    input.classList.add('error-input');
                    errorElement.style.display = 'block';
                    errorElement.textContent = 'يجب أن تكون الساعة بين 1 و 12';
                    return false;
                }
            } else {
                if (value < 0 || value > 59) {
                    input.classList.add('error-input');
                    errorElement.style.display = 'block';
                    errorElement.textContent = 'يجب أن تكون الدقيقة بين 0 و 59';
                    return false;
                }
            }
            
            input.classList.remove('error-input');
            errorElement.style.display = 'none';
            return true;
        }
        
        // إضافة مستمعات الأحداث لحقول الوقت
        const timeInputs = [
            {id: 'plannedStartHour', isHour: true},
            {id: 'plannedStartMinute', isHour: false},
            {id: 'actualStartHour', isHour: true},
            {id: 'actualStartMinute', isHour: false},
            {id: 'contactHour', isHour: true},
            {id: 'contactMinute', isHour: false},
            {id: 'endHour', isHour: true},
            {id: 'endMinute', isHour: false}
        ];
        
        timeInputs.forEach(input => {
            const element = document.getElementById(input.id);
            element.addEventListener('blur', () => validateTime(element, input.isHour));
            element.addEventListener('input', () => {
                const errorId = element.id + 'Error';
                document.getElementById(errorId).style.display = 'none';
                element.classList.remove('error-input');
            });
        });
        
        // التحقق من جميع الأوقات
        function validateAllTimes() {
            let isValid = true;
            
            timeInputs.forEach(input => {
                const element = document.getElementById(input.id);
                if (!validateTime(element, input.isHour)) {
                    isValid = false;
                }
            });
            
            return isValid;
        }
        
        // إظهار/إخفاء قسم الأسئلة الخاصة بالرمز الأحمر
        document.getElementById('codeType')
                    // إظهار/إخفاء قسم الأسئلة الخاصة بالرمز الأحمر في القسم السادس
        document.getElementById('section6CodeType').addEventListener('change', function() {
            // أول شي نخفي كل الأقسام
            Object.values(codeSectionMap).forEach(id => {
                const section = document.getElementById(id);
                if (section) section.classList.remove('show');
            });

            // بعدين نعرض القسم المختار
            const selectedSectionId = codeSectionMap[this.value];
            if (selectedSectionId) {
                const selectedSection = document.getElementById(selectedSectionId);
                if (selectedSection) selectedSection.classList.add('show');
            }
        });

                const codeSectionMap = {
            'الرمز الاحمر': 'redCodeSection',
            'الرمز الوردي': 'pinkCodeSection',
            'الرمز الفضي/الابيض': 'silverWhiteCodeSection',
            'الرمز الاصفر (اصابات متعددة)': 'yellowInjuryCodeSection',
            'الرمز الاصفر (امراض معدية)': 'yellowInfectionCodeSection',
            'الرمز الرمادي': 'grayCodeSection',
            'الرمز الاسود': 'blackCodeSection',
            'الرمز البرتقالي': 'orangeCodeSection',
            'الرمز البني': 'brownCodeSection'
        };

        document.getElementById('section6CodeType').addEventListener('change', function () {
            // إخفاء جميع أقسام الرموز
            Object.values(codeSectionMap).forEach(id => {
                const section = document.getElementById(id);
                if (section) section.classList.remove('show');
            });

            // عرض القسم المختار فقط
            const selectedCode = this.value;
            const sectionId = codeSectionMap[selectedCode];
            if (sectionId && document.getElementById(sectionId)) {
                document.getElementById(sectionId).classList.add('show');
            }
        });

        
        // معالجة إرسال النموذج
        document.getElementById('surveyForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // التحقق من صحة الأوقات
            if (!validateAllTimes()) {
                alert('يرجى تصحيح الأخطاء في قسم تسجيل الوقت');
                return;
            }
            
            // عرض رسالة تأكيد
            alert('تم إرسال تقييم الفرضية بنجاح!\nالبيانات أرسلت إلى بريدك الإلكتروني');
            
            // إعادة تعيين النموذج
            this.reset();
            document.getElementById('otherTrainingInput').classList.remove('show');
            document.getElementById('otherCommunicationMethodInput').classList.remove('show');
            document.getElementById('otherRecordingMethodInput').classList.remove('show');
            document.getElementById('redCodeSection').classList.remove('show');
            setCurrentDate(); // إعادة تعيين التاريخ بعد الإرسال
        });
        
        // تعيين التاريخ عند تحميل الصفحة
        document.addEventListener('DOMContentLoaded', setCurrentDate);
        
        // شريط التقدم
        window.addEventListener('scroll', function() {
            const scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
            const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrollPercent = (scrollTop / scrollHeight) * 100;
            document.getElementById('progressBar').style.width = scrollPercent + '%';
            
            // زر التمرير للأعلى
            const scrollTopBtn = document.getElementById('scrollTopBtn');
            if (scrollTop > 300) {
                scrollTopBtn.classList.add('visible');
            } else {
                scrollTopBtn.classList.remove('visible');
            }
        });
        
        // التمرير للأعلى عند النقر على الزر
        document.getElementById('scrollTopBtn').addEventListener('click', function() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
    </script>
</body>
</html>
