# SITHCCC031-Workshop-Feedback-Survey
Feedback for Workshop on SITHCCC031 Prepare Vegetarian and Vegan Dishes
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Workshop Feedback Survey - SITHCCC031</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .header p {
            font-size: 16px;
            opacity: 0.9;
        }

        .form-content {
            padding: 40px;
        }

        .section {
            margin-bottom: 35px;
        }

        .section-title {
            font-size: 20px;
            font-weight: 600;
            color: #333;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #4CAF50;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #555;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 14px;
            transition: all 0.3s ease;
            background: rgba(255, 255, 255, 0.8);
        }

        .form-control:focus {
            outline: none;
            border-color: #4CAF50;
            box-shadow: 0 0 15px rgba(76, 175, 80, 0.2);
            background: white;
        }

        .rating-container {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 10px;
        }

        .rating-item {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px 15px;
            border: 2px solid #ddd;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: rgba(255, 255, 255, 0.8);
        }

        .rating-item:hover {
            border-color: #4CAF50;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.2);
        }

        .rating-item input[type="radio"] {
            margin: 0;
        }

        .rating-item.selected {
            background: linear-gradient(135deg, #4CAF50, #45a049);
            border-color: #4CAF50;
            color: white;
        }

        textarea.form-control {
            min-height: 100px;
            resize: vertical;
        }

        .checkbox-group {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin-top: 10px;
        }

        .checkbox-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: rgba(255, 255, 255, 0.8);
        }

        .checkbox-item:hover {
            border-color: #4CAF50;
            transform: translateY(-1px);
        }

        .checkbox-item.selected {
            background: rgba(76, 175, 80, 0.1);
            border-color: #4CAF50;
        }

        .checkbox-item input[type="checkbox"] {
            margin: 0;
            transform: scale(1.2);
        }

        .submit-btn {
            background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
            color: white;
            border: none;
            padding: 15px 40px;
            border-radius: 25px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 25px rgba(76, 175, 80, 0.3);
            display: block;
            margin: 30px auto 0;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 35px rgba(76, 175, 80, 0.4);
        }

        .required {
            color: #e74c3c;
        }

        .response-display {
            margin-top: 30px;
            padding: 20px;
            background: rgba(76, 175, 80, 0.1);
            border-radius: 15px;
            border: 2px solid #4CAF50;
            display: none;
        }
        
        .response-display h3 {
            color: #4CAF50;
            margin-bottom: 15px;
        }
        
        .response-item {
            background: white;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 10px;
            border-left: 4px solid #4CAF50;
        }

        /* ADMIN PANEL STYLES */
        .admin-toggle {
            position: fixed;
            top: 15px;
            right: 15px;
            background: #FF6B35;
            color: white;
            border: none;
            padding: 20px 25px;
            border-radius: 30px;
            cursor: pointer;
            z-index: 10001;
            font-size: 18px;
            font-weight: bold;
            box-shadow: 0 8px 20px rgba(255, 107, 53, 0.4);
            animation: adminPulse 2s infinite;
            transition: all 0.3s ease;
        }

        @keyframes adminPulse {
            0% { transform: scale(1); box-shadow: 0 8px 20px rgba(255, 107, 53, 0.4); }
            50% { transform: scale(1.05); box-shadow: 0 12px 30px rgba(255, 107, 53, 0.6); }
            100% { transform: scale(1); box-shadow: 0 8px 20px rgba(255, 107, 53, 0.4); }
        }

        .admin-toggle:hover {
            background: #E55A2B;
            transform: scale(1.1);
        }

        .admin-panel {
            position: fixed;
            top: 80px;
            right: 15px;
            background: rgba(0, 0, 0, 0.95);
            color: white;
            padding: 25px;
            border-radius: 15px;
            font-family: 'Courier New', monospace;
            font-size: 13px;
            max-width: 400px;
            max-height: 600px;
            overflow-y: auto;
            display: none;
            z-index: 10000;
            border: 3px solid #FF6B35;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.6);
        }

        .admin-panel h4 {
            color: #FF6B35;
            margin-bottom: 15px;
            font-size: 16px;
        }

        .close-admin {
            background: #ff4444;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            float: right;
            margin-bottom: 15px;
            font-size: 12px;
        }

        .admin-controls {
            margin-bottom: 20px;
            clear: both;
        }

        .admin-controls button {
            background: #4CAF50;
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 5px;
            margin-right: 5px;
            margin-bottom: 5px;
            cursor: pointer;
            font-size: 11px;
        }

        .admin-controls .clear-btn {
            background: #ff4444;
        }

        .response-entry {
            border-bottom: 1px solid #333;
            padding: 15px 0;
            margin-bottom: 15px;
        }

        .response-entry:last-child {
            border-bottom: none;
        }

        .response-header {
            color: #FF6B35;
            font-weight: bold;
            margin-bottom: 8px;
        }

        .response-data {
            font-size: 12px;
            line-height: 1.4;
        }

        /* Mobile Styles */
        @media (max-width: 768px) {
            .container {
                margin: 10px;
                border-radius: 15px;
            }
            
            .form-content {
                padding: 20px;
            }
            
            .header {
                padding: 20px;
            }
            
            .rating-container {
                flex-direction: column;
            }
            
            .checkbox-group {
                grid-template-columns: 1fr;
            }

            .admin-toggle {
                top: 10px;
                right: 10px;
                padding: 15px 20px;
                font-size: 16px;
            }

            .admin-panel {
                top: 70px;
                right: 10px;
                left: 10px;
                max-width: none;
                max-height: 70vh;
            }
        }
    </style>
</head>
<body>
    <!-- ADMIN BUTTON - BRIGHT ORANGE, IMPOSSIBLE TO MISS -->
    <button class="admin-toggle" onclick="toggleAdmin()" title="Click to view all feedback responses">
        🔍 VIEW RESPONSES
    </button>

    <!-- ADMIN PANEL -->
    <div class="admin-panel" id="adminPanel">
        <button class="close-admin" onclick="toggleAdmin()">✕ Close</button>
        <h4>📊 Workshop Feedback Responses</h4>
        <div class="admin-controls">
            <span style="color: #ccc; font-size: 11px;">Total Responses: <span id="responseCount">0</span></span><br><br>
            <button onclick="exportResponses()" title="Copy all responses to clipboard">📋 Export All</button>
            <button onclick="clearResponses()" class="clear-btn" title="Delete all responses">🗑️ Clear All</button>
        </div>
        <div id="adminContent">
            <div style="text-align: center; color: #666; font-style: italic;">
                No responses yet...<br>
                Share your form URL to start collecting feedback!
            </div>
        </div>
    </div>

    <div class="container">
        <div class="header">
            <h1>🥗 Workshop Feedback Survey</h1>
            <p>SITHCCC031 - Prepare Vegetarian and Vegan Dishes</p>
        </div>

        <div class="form-content">
            <form id="feedbackForm">
                <div class="section">
                    <h2 class="section-title">Workshop Content & Delivery</h2>
                    
                    <div class="form-group">
                        <label>Overall, how would you rate this Miro workshop? <span class="required">*</span></label>
                        <div class="rating-container">
                            <div class="rating-item">
                                <input type="radio" name="overall_rating" value="5" id="overall_5" required>
                                <label for="overall_5">⭐⭐⭐⭐⭐ Excellent</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="overall_rating" value="4" id="overall_4">
                                <label for="overall_4">⭐⭐⭐⭐ Good</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="overall_rating" value="3" id="overall_3">
                                <label for="overall_3">⭐⭐⭐ Fair</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="overall_rating" value="2" id="overall_2">
                                <label for="overall_2">⭐⭐ Poor</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="overall_rating" value="1" id="overall_1">
                                <label for="overall_1">⭐ Very Poor</label>
                            </div>
                        </div>
                    </div>

                    <div class="form-group">
                        <label>How clear and organized was the content presentation? <span class="required">*</span></label>
                        <div class="rating-container">
                            <div class="rating-item">
                                <input type="radio" name="content_clarity" value="5" id="clarity_5" required>
                                <label for="clarity_5">Very Clear</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="content_clarity" value="4" id="clarity_4">
                                <label for="clarity_4">Clear</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="content_clarity" value="3" id="clarity_3">
                                <label for="clarity_3">Somewhat Clear</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="content_clarity" value="2" id="clarity_2">
                                <label for="clarity_2">Unclear</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="content_clarity" value="1" id="clarity_1">
                                <label for="clarity_1">Very Unclear</label>
                            </div>
                        </div>
                    </div>

                    <div class="form-group">
                        <label>How would you rate the use of Miro as a presentation tool for this workshop?</label>
                        <div class="rating-container">
                            <div class="rating-item">
                                <input type="radio" name="miro_effectiveness" value="5" id="miro_5">
                                <label for="miro_5">Very Effective</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="miro_effectiveness" value="4" id="miro_4">
                                <label for="miro_4">Effective</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="miro_effectiveness" value="3" id="miro_3">
                                <label for="miro_3">Neutral</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="miro_effectiveness" value="2" id="miro_2">
                                <label for="miro_2">Ineffective</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="miro_effectiveness" value="1" id="miro_1">
                                <label for="miro_1">Very Ineffective</label>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">Learning Outcomes</h2>
                    
                    <div class="form-group">
                        <label>Which aspects of vegetarian and vegan dish preparation were covered well? (Select all that apply)</label>
                        <div class="checkbox-group">
                            <div class="checkbox-item">
                                <input type="checkbox" name="topics_covered" value="ingredient_selection" id="topic_1">
                                <label for="topic_1">Ingredient Selection & Sourcing</label>
                            </div>
                            <div class="checkbox-item">
                                <input type="checkbox" name="topics_covered" value="nutritional_balance" id="topic_2">
                                <label for="topic_2">Nutritional Balance</label>
                            </div>
                            <div class="checkbox-item">
                                <input type="checkbox" name="topics_covered" value="cooking_techniques" id="topic_3">
                                <label for="topic_3">Cooking Techniques</label>
                            </div>
                            <div class="checkbox-item">
                                <input type="checkbox" name="topics_covered" value="flavor_development" id="topic_4">
                                <label for="topic_4">Flavor Development</label>
                            </div>
                            <div class="checkbox-item">
                                <input type="checkbox" name="topics_covered" value="presentation" id="topic_5">
                                <label for="topic_5">Presentation & Plating</label>
                            </div>
                            <div class="checkbox-item">
                                <input type="checkbox" name="topics_covered" value="menu_planning" id="topic_6">
                                <label for="topic_6">Menu Planning</label>
                            </div>
                        </div>
                    </div>

                    <div class="form-group">
                        <label>How confident do you feel about preparing vegetarian/vegan dishes after this workshop?</label>
                        <div class="rating-container">
                            <div class="rating-item">
                                <input type="radio" name="confidence_level" value="5" id="conf_5">
                                <label for="conf_5">Very Confident</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="confidence_level" value="4" id="conf_4">
                                <label for="conf_4">Confident</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="confidence_level" value="3" id="conf_3">
                                <label for="conf_3">Somewhat Confident</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="confidence_level" value="2" id="conf_2">
                                <label for="conf_2">Not Very Confident</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="confidence_level" value="1" id="conf_1">
                                <label for="conf_1">Not Confident</label>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">Feedback & Suggestions</h2>
                    
                    <div class="form-group">
                        <label>What did you find most valuable about this workshop?</label>
                        <textarea class="form-control" name="most_valuable" placeholder="Please share what aspects of the workshop were most helpful or interesting to you..."></textarea>
                    </div>

                    <div class="form-group">
                        <label>What areas could be improved or expanded upon?</label>
                        <textarea class="form-control" name="improvements" placeholder="Please suggest any improvements or additional topics you'd like to see covered..."></textarea>
                    </div>

                    <div class="form-group">
                        <label>Any additional comments or suggestions?</label>
                        <textarea class="form-control" name="additional_comments" placeholder="Feel free to share any other thoughts, suggestions, or feedback..."></textarea>
                    </div>

                    <div class="form-group">
                        <label>Would you recommend this workshop to other culinary students?</label>
                        <div class="rating-container">
                            <div class="rating-item">
                                <input type="radio" name="recommend" value="definitely" id="rec_def">
                                <label for="rec_def">👍 Definitely Yes</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="recommend" value="probably" id="rec_prob">
                                <label for="rec_prob">✅ Probably Yes</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="recommend" value="maybe" id="rec_maybe">
                                <label for="rec_maybe">🤔 Maybe</label>
                            </div>
                            <div class="rating-item">
                                <input type="radio" name="recommend" value="probably_not" id="rec_no">
                                <label for="rec_no">❌ Probably Not</label>
                            </div>
                        </div>
                    </div>
                </div>

                <button type="submit" class="submit-btn">Submit Feedback</button>
                
                <div class="response-display" id="responseDisplay">
                    <h3>📋 Response Submitted Successfully!</h3>
                    <div id="responseContent"></div>
                </div>
            </form>
        </div>
    </div>

    <script>
        // Store all responses
        let allResponses = [];

        // Admin panel functions
        function toggleAdmin() {
            const panel = document.getElementById('adminPanel');
            panel.style.display = panel.style.display === 'block' ? 'none' : 'block';
        }

        function clearResponses() {
            if (confirm('⚠️ Are you sure you want to delete ALL responses? This cannot be undone!')) {
                allResponses = [];
                document.getElementById('adminContent').innerHTML = '<div style="text-align: center; color: #666; font-style: italic;">All responses cleared!<br>Share your form URL to start collecting new feedback.</div>';
                document.getElementById('responseCount').textContent = '0';
                localStorage.removeItem('workshopResponses');
                alert('✅ All responses have been cleared successfully.');
            }
        }

        function exportResponses() {
            if (allResponses.length === 0) {
                alert('❌ No responses to export yet. Wait for students to submit feedback first.');
                return;
            }
            
            const exportText = 'SITHCCC031 WORKSHOP FEEDBACK SUMMARY\n' +
                              'Total Responses: ' + allResponses.length + '\n' +
                              'Export Date: ' + new Date().toLocaleString() + '\n' +
                              '============================================================\n\n' +
                              allResponses.map(function(response, index) {
                                return 'RESPONSE #' + (index + 1) + '\n' +
                    'Overall Rating: ' + (response.overall_rating || 'Not provided') + '/5 stars\n' +
                    'Content Clarity: ' + (response.content_clarity || 'Not provided') + '/5\n' +
                    'Miro Effectiveness: ' + (response.miro_effectiveness || 'Not provided') + '/5\n' +
                    'Confidence Level: ' + (response.confidence_level || 'Not provided') + '/5\n' +
                    'Topics Covered Well: ' + (Array.isArray(response.topics_covered) ? response.topics_covered.join(', ') : (response.topics_covered || 'None selected')) + '\n' +
                    'Most Valuable: ' + (response.most_valuable || 'No comment') + '\n' +
                    'Improvements Suggested: ' + (response.improvements || 'No suggestions') + '\n' +
                    'Additional Comments: ' + (response.additional_comments || 'No additional comments') + '\n' +
                    'Would Recommend: ' + (response.recommend || 'Not specified') + '\n' +
                    '----------------------------------------\n';
            }).join('\n');
            
            navigator.clipboard.writeText(exportText).then(function() {
                alert('✅ All ' + allResponses.length + ' responses exported to clipboard!\n\nYou can now paste this into a Word document, email, or text file for analysis.');
            }).catch(function() {
                // Fallback: show in new window
                const newWindow = window.open('', '_blank');
                newWindow.document.write('<pre style="font-family: monospace; padding: 20px; line-height: 1.4;">' + exportText + '</pre>');
                alert('📄 Responses opened in new window. Copy the text from there.');
            });
        }

        function updateAdminPanel(responseData) {
            const adminContent = document.getElementById('adminContent');
            
            // Create response entry
            const responseDiv = document.createElement('div');
            responseDiv.className = 'response-entry';
            
            const timestamp = new Date().toLocaleString();
            responseDiv.innerHTML = '<div class="response-header">Response #' + allResponses.length + ' - ' + timestamp + '</div>' +
                '<div class="response-data">' +
                    '<strong>⭐ Overall:</strong> ' + (responseData.overall_rating || 'N/A') + '/5<br>' +
                    '<strong>📊 Clarity:</strong> ' + (responseData.content_clarity || 'N/A') + '/5<br>' +
                    '<strong>💻 Miro:</strong> ' + (responseData.miro_effectiveness || 'N/A') + '/5<br>' +
                    '<strong>🎯 Confidence:</strong> ' + (responseData.confidence_level || 'N/A') + '/5<br>' +
                    '<strong>👍 Recommend:</strong> ' + (responseData.recommend || 'N/A') + '<br>' +
                    (responseData.most_valuable ? '<strong>💡 Most Valuable:</strong> ' + responseData.most_valuable.substring(0, 100) + (responseData.most_valuable.length > 100 ? '...' : '') + '<br>' : '') +
                    (responseData.improvements ? '<strong>🔧 Improvements:</strong> ' + responseData.improvements.substring(0, 100) + (responseData.improvements.length > 100 ? '...' : '') + '<br>' : '') +
                '</div>';
            
            // Clear "no responses" message if this is first response
            if (allResponses.length === 1) {
                adminContent.innerHTML = '';
            }
            
            // Add new response at top
            adminContent.insertBefore(responseDiv, adminContent.firstChild);
            
            // Update response count
            document.getElementById('responseCount').textContent = allResponses.length;
        }

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            // Load saved responses from previous sessions
            const savedResponses = localStorage.getItem('workshopResponses');
            if (savedResponses) {
                try {
                    allResponses = JSON.parse(savedResponses);
                    allResponses.forEach(function(response) {
                        updateAdminPanel(response);
                    });
                } catch(e) {
                    console.log('Error loading saved responses:', e);
                    localStorage.removeItem('workshopResponses');
                }
            }

            // Handle radio button styling
            const radioItems = document.querySelectorAll('.rating-item');
            radioItems.forEach(function(item) {
                const radio = item.querySelector('input[type="radio"]');
                if (radio) {
                    radio.addEventListener('change', function() {
                        const groupName = this.name;
                        document.querySelectorAll('input[name="' + groupName + '"]').forEach(function(r) {
                            r.closest('.rating-item').classList.remove('selected');
                        });
                        this.closest('.rating-item').classList.add('selected');
                    });
                }
            });

            // Handle checkbox styling
            const checkboxItems = document.querySelectorAll('.checkbox-item');
            checkboxItems.forEach(function(item) {
                const checkbox = item.querySelector('input[type="checkbox"]');
                if (checkbox) {
                    checkbox.addEventListener('change', function() {
                        if (this.checked) {
                            this.closest('.checkbox-item').classList.add('selected');
                        } else {
                            this.closest('.checkbox-item').classList.remove('selected');
                        }
                    });
                }
            });

            // Handle form submission
            document.getElementById('feedbackForm').addEventListener('submit', function(e) {
                e.preventDefault();
                
                // Collect form data
                const formData = new FormData(this);
                const responses = {};
                
                // Convert form data to readable format
                for (const entry of formData.entries()) {
                    const key = entry[0];
                    const value = entry[1];
                    if (responses[key]) {
                        if (Array.isArray(responses[key])) {
                            responses[key].push(value);
                        } else {
                            responses[key] = [responses[key], value];
                        }
                    } else {
                        responses[key] = value;
                    }
                }

                // Add timestamp
                responses.submitted_at = new Date().toISOString();

                // Add to responses array
                allResponses.push(responses);
                
                // Save to localStorage for persistence
                localStorage.setItem('workshopResponses', JSON.stringify(allResponses));
                
                // Update admin panel
                updateAdminPanel(responses);

                // Show confirmation to user
                const responseDisplay = document.getElementById('responseDisplay');
                const responseContent = document.getElementById('responseContent');
                
                responseContent.innerHTML = '<div class="response-item">' +
                        '<strong>✅ Your feedback has been recorded!</strong><br><br>' +
                        '<strong>Overall Rating:</strong> ' + (responses.overall_rating || 'Not rated') + '/5 stars<br>' +
                        '<strong>Content Clarity:</strong> ' + (responses.content_clarity || 'Not rated') + '/5<br>' +
                        '<strong>Confidence Level:</strong> ' + (responses.confidence_level || 'Not rated') + '/5<br>' +
                        '<strong>Recommendation:</strong> ' + (responses.recommend || 'Not specified') + '<br>' +
                        (responses.most_valuable ? '<strong>Most Valuable:</strong> ' + responses.most_valuable + '<br>' : '') +
                        (responses.improvements ? '<strong>Improvements:</strong> ' + responses.improvements + '<br>' : '') +
                        '<br><small><em>Submitted: ' + new Date().toLocaleString() + '</em></small>' +
                    '</div>';
                
                responseDisplay.style.display = 'block';
                
                // Show success message
                alert('✅ Thank you for your feedback! Your responses have been recorded successfully.');
                
                // Clear the form
                this.reset();
                
                // Remove selected styling
                document.querySelectorAll('.rating-item.selected, .checkbox-item.selected').forEach(function(item) {
                    item.classList.remove('selected');
                });

                // Scroll to response display
                responseDisplay.scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>
