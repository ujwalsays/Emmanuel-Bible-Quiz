<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emmanual Ministry Bible Quiz</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            background: linear-gradient(to bottom, #1e3a8a, #3b82f6);
            color: #1c2526;
            font-family: 'Georgia', serif;
        }
        .quiz-container {
            background: #f8f1e9;
            border: 2px solid #d4af37;
            border-radius: 12px;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
        }
        .header-icon {
            display: inline-block;
            width: 30px;
            height: 30px;
            background: url('https://img.icons8.com/ios/50/d4af37/dove.png') no-repeat center;
            background-size: contain;
        }
        button {
            background: linear-gradient(to right, #d4af37, #b89727);
            transition: background 0.3s;
        }
        button:hover {
            background: linear-gradient(to right, #b89727, #a68b1f);
        }
        input[type="text"], input[type="email"] {
            background: #fefcfa;
            border-color: #d4af37;
        }
        .question-box {
            background: #fefcfa;
            border-color: #d4af37;
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center">
    <div class="quiz-container max-w-3xl w-full p-8 m-4">
        <h1 class="text-4xl font-bold text-center mb-6 flex items-center justify-center">
            <span class="header-icon mr-2"></span>
            Emmanual Ministry Bible Quiz
            <span class="header-icon ml-2"></span>
        </h1>
        <h2 class="text-2xl font-semibold text-center mb-4">विषय: बाइबल ज्ञान</h2>
        <p class="text-center mb-4">कुल अंक: 30 | समय: 30 मिनट</p>
        <p class="text-center mb-6 italic">निर्देश: सभी प्रश्नों के उत्तर दें।</p>

        <form id="quizForm" action="YOUR_GOOGLE_APPS_SCRIPT_URL" method="POST">
            <!-- Hidden Submission ID -->
            <input type="hidden" name="submission_id" id="submissionId">

            <!-- Attendee Name and Email -->
            <div class="mb-6">
                <label for="attendeeName" class="block text-lg font-medium mb-2">नाम (Name):</label>
                <input type="text" id="attendeeName" name="attendeeName" required class="w-full p-2 border rounded">
                <label for="attendeeEmail" class="block text-lg font-medium mt-4 mb-2">ईमेल (Email, Optional):</label>
                <input type="email" id="attendeeEmail" name="attendeeEmail" class="w-full p-2 border rounded">
            </div>

            <!-- Section A: Multiple Choice -->
            <h3 class="text-xl font-semibold mb-4">खंड A: सही उत्तर पर टिक करें (प्रत्येक प्रश्न 1 अंक)</h3>
            <div class="space-y-6">
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">1. यीशु मसीह का जन्म कहाँ हुआ था?</p>
                    <label class="block"><input type="radio" name="q1" value="यरूशलेम" required class="mr-2"> यरूशलेम</label>
                    <label class="block"><input type="radio" name="q1" value="नासरत" class="mr-2"> नासरत</label>
                    <label class="block"><input type="radio" name="q1" value="बेतलहम" class="mr-2"> बेतलहम</label>
                    <label class="block"><input type="radio" name="q1" value="किस" class="mr-2"> किस</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">2. बाइबल के पहले पुस्तक का नाम क्या है?</p>
                    <label class="block"><input type="radio" name="q2" value="उत्पत्ति" required class="mr-2"> उत्पत्ति</label>
                    <label class="block"><input type="radio" name="q2" value="निर्गमन" class="mr-2"> निर्गमन</label>
                    <label class="block"><input type="radio" name="q2" value="भजन संहिता" class="mr-2"> भजन संहिता</label>
                    <label class="block"><input type="radio" name="q2" value="हितोपदेश" class="mr-2"> हितोपदेश</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">3. यीशु ने कितने शिष्यों को चुना था?</p>
                    <label class="block"><input type="radio" name="q3" value="10" required class="mr-2"> 10</label>
                    <label class="block"><input type="radio" name="q3" value="70" class="mr-2"> 70</label>
                    <label class="block"><input type="radio" name="q3" value="12" class="mr-2"> 12</label>
                    <label class="block"><input type="radio" name="q3" value="7" class="mr-2"> 7</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">4. बाइबल कितने भागों में विभाजित है?</p>
                    <label class="block"><input type="radio" name="q4" value="एक" required class="mr-2"> एक</label>
                    <label class="block"><input type="radio" name="q4" value="दो" class="mr-2"> दो</label>
                    <label class="block"><input type="radio" name="q4" value="तीन" class="mr-2"> तीन</label>
                    <label class="block"><input type="radio" name="q4" value="चार" class="mr-2"> चार</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">5. 'प्रेम' का अध्याय किस पुस्तक में आता है?</p>
                    <label class="block"><input type="radio" name="q5" value="हितोपदेश 5" required class="mr-2"> हितोपदेश 5</label>
                    <label class="block"><input type="radio" name="q5" value="1 कुरिन्थियों 13" class="mr-2"> 1 कुरिन्थियों 13</label>
                    <label class="block"><input type="radio" name="q5" value="भजन संहिता 23" class="mr-2"> भजन संहिता 23</label>
                    <label class="block"><input type="radio" name="q5" value="यूहन्ना 8" class="mr-2"> यूहन्ना 8</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">6. बाइबल का सबसे लंबा भजन कौन-सा है?</p>
                    <label class="block"><input type="radio" name="q6" value="भजन संहिता 1" required class="mr-2"> भजन संहिता 1</label>
                    <label class="block"><input type="radio" name="q6" value="भजन संहिता 23" class="mr-2"> भजन संहिता 23</label>
                    <label class="block"><input type="radio" name="q6" value="भजन संहिता 91" class="mr-2"> भजन संहिता 91</label>
                    <label class="block"><input type="radio" name="q6" value="भजन संहिता 119" class="mr-2"> भजन संहिता 119</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">7. यीशु मसीह को किसने धोखा दिया था?</p>
                    <label class="block"><input type="radio" name="q7" value="पतरस" required class="mr-2"> पतरस</label>
                    <label class="block"><input type="radio" name="q7" value="यूहन्ना" class="mr-2"> यूहन्ना</label>
                    <label class="block"><input type="radio" name="q7" value="यहूदा" class="mr-2"> यहूदा</label>
                    <label class="block"><input type="radio" name="q7" value="थोमा" class="mr-2"> थोमा</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">8. किसने जल में चलने की कोशिश की थी लेकिन डर के कारण डूबने लगा?</p>
                    <label class="block"><input type="radio" name="q8" value="यूहन्ना" required class="mr-2"> यूहन्ना</label>
                    <label class="block"><input type="radio" name="q8" value="पतरस" class="mr-2"> पतरस</label>
                    <label class="block"><input type="radio" name="q8" value="याकूब" class="mr-2"> याकूब</label>
                    <label class="block"><input type="radio" name="q8" value="अन्द्रियास" class="mr-2"> अन्द्रियास</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">9. यीशु का जन्म किस कुंवारी से हुआ था?</p>
                    <label class="block"><input type="radio" name="q9" value="मार्था" required class="mr-2"> मार्था</label>
                    <label class="block"><input type="radio" name="q9" value="मरियम" class="mr-2"> मरियम</label>
                    <label class="block"><input type="radio" name="q9" value="मरियम मगदलीनी" class="mr-2"> मरियम मगदलीनी</label>
                    <label class="block"><input type="radio" name="q9" value="सारा" class="mr-2"> सारा</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">10. बाइबल की अंतिम पुस्तक का नाम क्या है?</p>
                    <label class="block"><input type="radio" name="q10" value="यशायाह" required class="mr-2"> यशायाह</label>
                    <label class="block"><input type="radio" name="q10" value="यूहन्ना" class="mr-2"> यूहन्ना</label>
                    <label class="block"><input type="radio" name="q10" value="प्रकाशितवाक्य" class="mr-2"> प्रकाशितवाक्य</label>
                    <label class="block"><input type="radio" name="q10" value="हितोपदेश" class="mr-2"> हितोपदेश</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">11. परमेश्वर ने संसार को किसके द्वारा रचा?</p>
                    <label class="block"><input type="radio" name="q11" value="यूहन्ना" required class="mr-2"> यूहन्ना</label>
                    <label class="block"><input type="radio" name="q11" value="इब्राहीम" class="mr-2"> इब्राहीम</label>
                    <label class="block"><input type="radio" name="q11" value="वचन (Word)" class="mr-2"> वचन (Word)</label>
                    <label class="block"><input type="radio" name="q11" value="मूसा" class="mr-2"> मूसा</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">12. मसीही विश्वास के अनुसार उद्धार किसके द्वारा होता है?</p>
                    <label class="block"><input type="radio" name="q12" value="अच्छे कर्मों से" required class="mr-2"> अच्छे कर्मों से</label>
                    <label class="block"><input type="radio" name="q12" value="धन से" class="mr-2"> धन से</label>
                    <label class="block"><input type="radio" name="q12" value="विश्वास द्वारा" class="mr-2"> विश्वास द्वारा</label>
                    <label class="block"><input type="radio" name="q12" value="उपवास से" class="mr-2"> उपवास से</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">13. किसके द्वारा दस आज्ञाएँ दी गई थीं?</p>
                    <label class="block"><input type="radio" name="q13" value="इब्राहीम" required class="mr-2"> इब्राहीम</label>
                    <label class="block"><input type="radio" name="q13" value="मूसा" class="mr-2"> मूसा</label>
                    <label class="block"><input type="radio" name="q13" value="दाऊद" class="mr-2"> दाऊद</label>
                    <label class="block"><input type="radio" name="q13" value="यशायाह" class="mr-2"> यशायाह</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">14. किसने कहा, "मैं और मेरा घराना यहोवा की सेवा करेंगे"?</p>
                    <label class="block"><input type="radio" name="q14" value="यहोशू" required class="mr-2"> यहोशू</label>
                    <label class="block"><input type="radio" name="q14" value="इब्राहीम" class="mr-2"> इब्राहीम</label>
                    <label class="block"><input type="radio" name="q14" value="मूसा" class="mr-2"> मूसा</label>
                    <label class="block"><input type="radio" name="q14" value="दाऊद" class="mr-2"> दाऊद</label>
                </div>
                <div class="question-box p-4 rounded border">
                    <p class="font-medium">15. बाइबल के अनुसार परमेश्वर हैं।</p>
                    <label class="block"><input type="radio" name="q15" value="न्यायी" required class="mr-2"> न्यायी</label>
                    <label class="block"><input type="radio" name="q15" value="सर्वशक्तिमान" class="mr-2"> सर्वशक्तिमान</label>
                    <label class="block"><input type="radio" name="q15" value="सर्वत्र विद्यमान" class="mr-2"> सर्वत्र विद्यमान</label>
                    <label class="block"><input type="radio" name="q15" value="सर्वज्ञ" class="mr-2"> सर्वज्ञ</label>
                </div>
            </div>

            <!-- Section B: Fill in the Blanks -->
            <h3 class="text-xl font-semibold mt-8 mb-4">खंड B: रिक्त स्थान भरें (प्रत्येक प्रश्न 1 अंक)</h3>
            <div class="space-y-4">
                <div class="question-box p-4 rounded border">
                    <p>1. परमेश्वर ने संसार से ऐसा ____ किया कि उसने अपना इकलौता पुत्र दे दिया।</p>
                    <input type="text" name="b1" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>2. नोए ने ____ के निर्माण की आज्ञा पाई थी।</p>
                    <input type="text" name="b2" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>3. यीशु ने ____ दिन बाद मृतकों में से पुनरुत्थान किया।</p>
                    <input type="text" name="b3" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>4. मूसा को दस आज्ञाएँ ____ पर्वत पर मिली थी।</p>
                    <input type="text" name="b4" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>5. दाऊद एक ____ था जब उसे परमेश्वर ने चुना।</p>
                    <input type="text" name="b5" required class="w-full p-2 border rounded">
                </div>
            </div>

            <!-- Section D: Fill in the Blanks -->
            <h3 class="text-xl font-semibold mt-8 mb-4">खंड D: रिक्त स्थान भरें (प्रत्येक प्रश्न 1 अंक)</h3>
            <div class="space-y-4">
                <div class="question-box p-4 rounded border">
                    <p>1. परमेश्वर ने ____ दिनों में सृष्टि की रचना की थी।</p>
                    <input type="text" name="d1" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>2. बाइबल के अनुसार, पाप की मजदूरी ____ है।</p>
                    <input type="text" name="d2" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>3. ____ नदी में यीशु ने बपतिस्मा लिया था।</p>
                    <input type="text" name="d3" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>4. यीशु ने कहा, "मैं ____ और जीवन भी हूँ।"</p>
                    <input type="text" name="d4" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>5. जब यीशु मसीह मरे, तब मंदिर का परदा ____ से ____ तक फट गया।</p>
                    <input type="text" name="d5" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>6. अब्राहम को उसके विश्वास के कारण ____ से ____ तक पुकारा गया।</p>
                    <input type="text" name="d6" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>7. बाइबल के अनुसार, बिना ____ के विश्वास मृत है।</p>
                    <input type="text" name="d7" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>8. ____ एक भविष्यद्वक्ता था और परमेश्वर की आवाज सुनता था।</p>
                    <input type="text" name="d8" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>9. परमेश्वर हमारा ____ और गढ़ है।</p>
                    <input type="text" name="d9" required class="w-full p-2 border rounded">
                </div>
                <div class="question-box p-4 rounded border">
                    <p>10. यीशु ने कहा, "मैं ____ का मार्ग, सत्य और जीवन हूँ।"</p>
                    <input type="text" name="d10" required class="w-full p-2 border rounded">
                </div>
            </div>

            <!-- Submit Button -->
            <button type="submit" class="mt-6 w-full text-white p-3 rounded text-lg">Submit Quiz</button>
        </form>

        <!-- Feedback Message -->
        <div id="feedback" class="mt-4 text-center hidden">
            <p id="feedbackMessage" class="text-lg"></p>
        </div>
    </div>

    <script>
        // Generate unique submission ID
        function generateSubmissionId() {
            return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function(c) {
                const r = Math.random() * 16 | 0, v = c === 'x' ? r : (r & 0x3 | 0x8);
                return v.toString(16);
            });
        }

        document.getElementById('quizForm').addEventListener('submit', async function(event) {
            event.preventDefault();
            const feedback = document.getElementById('feedback');
            const feedbackMessage = document.getElementById('feedbackMessage');

            // Set submission ID
            document.getElementById('submissionId').value = generateSubmissionId();

            try {
                const formData = new FormData(event.target);
                const data = {};
                formData.forEach((value, key) => { data[key] = value; });

                const response = await fetch(event.target.action, {
                    method: 'POST',
                    body: JSON.stringify(data),
                    headers: {
                        'Content-Type': 'application/json',
                        'Accept': 'application/json'
                    }
                });

                if (response.ok) {
                    feedback.classList.remove('hidden');
                    feedbackMessage.textContent = 'Quiz submitted successfully! Answers saved to Google Sheet.';
                    feedbackMessage.classList.remove('text-red-600');
                    feedbackMessage.classList.add('text-green-600');
                    event.target.reset();
                } else {
                    throw new Error('Submission failed');
                }
            } catch (error) {
                feedback.classList.remove('hidden');
                feedbackMessage.textContent = 'Error submitting quiz. Please try again.';
                feedbackMessage.classList.remove('text-green-600');
                feedbackMessage.classList.add('text-red-600');
            }
        });
    </script>
</body>
</html>
