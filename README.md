<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Complete Agricultural Management System</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
        }
        .navbar {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 2rem;
            border-radius: 15px;
            margin-bottom: 2rem;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 10px;
            z-index: 1000;
        }
        .navbar-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #667eea;
            display: flex;
            align-items: center;
        }
        .logo i {
            margin-right: 10px;
            font-size: 1.8rem;
        }
        .nav-links {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }
        .nav-link, .btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            text-decoration: none;
            color: #667eea;
            background: transparent;
            transition: all 0.3s ease;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
        }
        .nav-link:hover, .btn:hover {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
        }
        .hero {
            text-align: center;
            padding: 3rem 0;
            color: white;
        }
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }
        .feature-card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }
        .feature-card h3 {
            color: #667eea;
            margin-bottom: 1rem;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
        }
        .feature-card h3 i {
            margin-right: 10px;
            font-size: 1.5rem;
        }
        .form-container {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            margin: 2rem 0;
        }
        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
        }
        .form-section {
            background: #f8f9ff;
            padding: 1.5rem;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }
        .form-section h4 {
            color: #667eea;
            margin-bottom: 1rem;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
        }
        .form-group {
            margin-bottom: 1.5rem;
        }
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #333;
            font-weight: 500;
        }
        .form-group input, .form-group select {
            width: 100%;
            padding: 0.75rem;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }
        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: #667eea;
        }
        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 0.75rem 2rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            margin: 1rem 0;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }
        .btn-primary:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
        }
        .result-card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            margin: 2rem 0;
            border-left: 5px solid #667eea;
        }
        .hidden {
            display: none;
        }
        .loading {
            text-align: center;
            padding: 2rem;
        }
        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #667eea;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 2s linear infinite;
            margin: 0 auto 1rem;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .data-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin: 1rem 0;
        }
        .data-item {
            background: white;
            padding: 1rem;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .data-item h5 {
            color: #667eea;
            margin-bottom: 0.5rem;
        }
        .sensor-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        .sensor-card {
            background: white;
            border-radius: 8px;
            padding: 15px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            text-align: center;
            transition: transform 0.3s;
        }
        .sensor-card:hover {
            transform: translateY(-5px);
        }
        .sensor-value {
            font-size: 24px;
            font-weight: bold;
            color: #667eea;
            margin: 10px 0;
        }
        .sensor-label {
            font-size: 14px;
            color: #666;
        }
        .sensor-status {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 12px;
            font-size: 12px;
            margin-top: 5px;
        }
        .status-normal {
            background: #d4edda;
            color: #155724;
        }
        .status-warning {
            background: #fff3cd;
            color: #856404;
        }
        .upload-area {
            border: 2px dashed #667eea;
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            margin: 1rem 0;
            background: rgba(102, 126, 234, 0.05);
            cursor: pointer;
        }
        .upload-area:hover {
            background: rgba(102, 126, 234, 0.1);
        }
        .image-preview {
            max-width: 100%;
            max-height: 300px;
            margin: 1rem auto;
            display: none;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .recommendation-item {
            background: #f0f4ff;
            padding: 1rem;
            border-radius: 8px;
            margin: 0.5rem 0;
            border-left: 3px solid #667eea;
        }
        .confidence-level {
            display: inline-block;
            padding: 0.25rem 0.5rem;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
        }
        .high-confidence { background: #d4edda; color: #155724; }
        .medium-confidence { background: #fff3cd; color: #856404; }
        .low-confidence { background: #f8d7da; color: #721c24; }
        .confidence-bar {
            height: 8px;
            background: #e0e0e0;
            border-radius: 4px;
            overflow: hidden;
            margin: 0.5rem 0;
        }
        .confidence-fill {
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transition: width 1s ease;
        }
        .card {
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        .price-trend-up { color: #10b981; }
        .price-trend-down { color: #ef4444; }
        @media (max-width: 768px) {
            .navbar-content {
                flex-direction: column;
                gap: 1rem;
            }
            .hero h1 {
                font-size: 2rem;
            }
            .features-grid {
                grid-template-columns: 1fr;
            }
            .container {
                padding: 10px;
            }
            .form-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Navigation -->
        <nav class="navbar">
            <div class="navbar-content">
                <div class="logo">
                    <i class="fas fa-seedling"></i>
                    <span>Agricultural Management System</span>
                </div>
                <div class="nav-links">
                    <button class="nav-link" onclick="showSection('home')">
                        <i class="fas fa-home"></i> Dashboard
                    </button>
                    <button class="nav-link" onclick="showSection('crop-recommend')">
                        <i class="fas fa-seedling"></i> Crop Advisor
                    </button>
                    <button class="nav-link" onclick="showSection('fertilizer')">
                        <i class="fas fa-flask"></i> Fertilizer
                    </button>
                    <button class="nav-link" onclick="showSection('yield-predict')">
                        <i class="fas fa-chart-line"></i> Yield Prediction
                    </button>
                    <button class="nav-link" onclick="showSection('weather')">
                        <i class="fas fa-cloud-sun"></i> Weather
                    </button>
                    <button class="nav-link" onclick="showSection('disease-detection')">
                        <i class="fas fa-bug"></i> Disease Detection
                    </button>
                    <button class="nav-link" onclick="showSection('market-helper')">
                        <i class="fas fa-store"></i> Market Helper
                    </button>
                </div>
            </div>
        </nav>

        <!-- Home Section -->
        <section id="home" class="section">
            <div class="hero">
                <h1>Complete Agricultural Management System</h1>
                <p>AI-powered decision support with real-time analytics, market information, and comprehensive farming tools</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card" onclick="showSection('crop-recommend')">
                    <h3><i class="fas fa-seedling"></i> Smart Crop Advisor</h3>
                    <p>Multi-factor analysis with comprehensive crop database covering 50+ crops and regional variations.</p>
                </div>
                
                <div class="feature-card" onclick="showSection('fertilizer')">
                    <h3><i class="fas fa-flask"></i> Fertilizer Optimizer</h3>
                    <p>Precision nutrient calculations based on soil science and plant nutrition algorithms.</p>
                </div>
                
                <div class="feature-card" onclick="showSection('yield-predict')">
                    <h3><i class="fas fa-chart-line"></i> Yield Predictor</h3>
                    <p>Machine learning models trained on historical yield data and environmental factors.</p>
                </div>
                
                <div class="feature-card" onclick="showSection('weather')">
                    <h3><i class="fas fa-cloud-sun"></i> Weather Analytics</h3>
                    <p>Real-time weather integration with agricultural decision support algorithms.</p>
                </div>
                
                <div class="feature-card" onclick="showSection('disease-detection')">
                    <h3><i class="fas fa-bug"></i> Disease Detection</h3>
                    <p>AI-powered image analysis to identify crop diseases and recommend treatments.</p>
                </div>
                
                <div class="feature-card" onclick="showSection('market-helper')">
                    <h3><i class="fas fa-store"></i> Market Helper</h3>
                    <p>Real-time market prices, equipment rental, labor services, and government schemes.</p>
                </div>
            </div>

            <div class="form-container">
                <h2><i class="fas fa-tachometer-alt"></i> Live Farm Dashboard</h2>
                <div class="sensor-grid" id="liveSensorData">
                    <!-- Sensor data populated by JavaScript -->
                </div>
            </div>
        </section>

        <!-- Crop Recommendation Section -->
        <section id="crop-recommend" class="section hidden">
            <div class="form-container">
                <h2><i class="fas fa-seedling"></i> Enhanced Crop Advisor</h2>
                
                <div class="form-grid">
                    <div class="form-section">
                        <h4><i class="fas fa-vial"></i> Soil Analysis</h4>
                        <div class="form-group">
                            <label for="nitrogen">Nitrogen (N) ppm</label>
                            <input type="number" id="nitrogen" value="45" min="0" max="500">
                        </div>
                        <div class="form-group">
                            <label for="phosphorous">Phosphorous (P) ppm</label>
                            <input type="number" id="phosphorous" value="22" min="0" max="200">
                        </div>
                        <div class="form-group">
                            <label for="potassium">Potassium (K) ppm</label>
                            <input type="number" id="potassium" value="180" min="0" max="500">
                        </div>
                        <div class="form-group">
                            <label for="ph">pH Level</label>
                            <input type="number" id="ph" value="6.5" step="0.1" min="3" max="11">
                        </div>
                    </div>
                    
                    <div class="form-section">
                        <h4><i class="fas fa-cloud-sun"></i> Environment</h4>
                        <div class="form-group">
                            <label for="temperature">Temperature (°C)</label>
                            <input type="number" id="temperature" value="25" step="0.1">
                        </div>
                        <div class="form-group">
                            <label for="rainfall">Rainfall (mm)</label>
                            <input type="number" id="rainfall" value="800" min="0">
                        </div>
                        <div class="form-group">
                            <label for="humidity">Humidity (%)</label>
                            <input type="number" id="humidity" value="65" min="0" max="100">
                        </div>
                        <div class="form-group">
                            <label for="region">Region</label>
                            <select id="region">
                                <option value="Tropical">Tropical</option>
                                <option value="Subtropical">Subtropical</option>
                                <option value="Temperate">Temperate</option>
                                <option value="Arid">Arid</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="form-section">
                        <h4><i class="fas fa-mountain"></i> Soil Properties</h4>
                        <div class="form-group">
                            <label for="soil_type">Soil Type</label>
                            <select id="soil_type">
                                <option value="Loamy">Loamy</option>
                                <option value="Sandy">Sandy</option>
                                <option value="Clay">Clay</option>
                                <option value="Silt">Silt</option>
                                <option value="Peaty">Peaty</option>
                                <option value="Chalky">Chalky</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="organic_matter">Organic Matter (%)</label>
                            <input type="number" id="organic_matter" value="2.5" step="0.1" min="0" max="20">
                        </div>
                    </div>
                </div>
                
                <button type="button" class="btn-primary" onclick="getCropRecommendation()">
                    <i class="fas fa-calculator"></i> Generate Recommendations
                </button>
            </div>

            <div id="cropLoading" class="loading hidden">
                <div class="spinner"></div>
                <p>Analyzing soil conditions and generating recommendations...</p>
            </div>

            <div id="cropResult" class="result-card hidden">
                <h3><i class="fas fa-seedling"></i> Recommended Crops</h3>
                <div id="cropRecommendations"></div>
            </div>
        </section>

        <!-- Fertilizer Section -->
        <section id="fertilizer" class="section hidden">
            <div class="form-container">
                <h2><i class="fas fa-flask"></i> Precision Fertilizer Calculator</h2>
                
                <div class="form-grid">
                    <div class="form-section">
                        <h4><i class="fas fa-vial"></i> Current Soil Levels</h4>
                        <div class="form-group">
                            <label for="f_nitrogen">Nitrogen (N) ppm</label>
                            <input type="number" id="f_nitrogen" value="35" min="0" max="500">
                        </div>
                        <div class="form-group">
                            <label for="f_phosphorous">Phosphorous (P) ppm</label>
                            <input type="number" id="f_phosphorous" value="18" min="0" max="200">
                        </div>
                        <div class="form-group">
                            <label for="f_potassium">Potassium (K) ppm</label>
                            <input type="number" id="f_potassium" value="150" min="0" max="500">
                        </div>
                        <div class="form-group">
                            <label for="f_ph">Soil pH</label>
                            <input type="number" id="f_ph" value="6.5" step="0.1" min="3" max="11">
                        </div>
                    </div>
                    
                    <div class="form-section">
                        <h4><i class="fas fa-seedling"></i> Crop Information</h4>
                        <div class="form-group">
                            <label for="f_crop_type">Crop Type</label>
                            <select id="f_crop_type">
                                <option value="">Select Crop</option>
                                <option value="Rice">Rice</option>
                                <option value="Wheat">Wheat</option>
                                <option value="Corn">Corn</option>
                                <option value="Tomato">Tomato</option>
                                <option value="Potato">Potato</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="f_area">Farm Area (hectares)</label>
                            <input type="number" id="f_area" value="1" step="0.1" min="0.1">
                        </div>
                    </div>
                </div>
                
                <button type="button" class="btn-primary" onclick="getFertilizerRecommendation()">
                    <i class="fas fa-calculator"></i> Calculate Fertilizer Needs
                </button>
            </div>

            <div id="fertilizerLoading" class="loading hidden">
                <div class="spinner"></div>
                <p>Calculating optimal fertilizer requirements...</p>
            </div>

            <div id="fertilizerResult" class="result-card hidden">
                <h3><i class="fas fa-flask"></i> Fertilizer Recommendations</h3>
                <div id="fertilizerRecommendations"></div>
            </div>
        </section>

        <!-- Yield Prediction Section -->
        <section id="yield-predict" class="section hidden">
            <div class="form-container">
                <h2><i class="fas fa-chart-line"></i> AI Yield Prediction Model</h2>
                
                <div class="form-grid">
                    <div class="form-section">
                        <h4><i class="fas fa-seedling"></i> Crop Details</h4>
                        <div class="form-group">
                            <label for="y_crop">Crop Type</label>
                            <select id="y_crop">
                                <option value="">Select Crop</option>
                                <option value="Rice">Rice</option>
                                <option value="Wheat">Wheat</option>
                                <option value="Corn">Corn</option>
                                <option value="Soybean">Soybean</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="y_area">Cultivated Area (ha)</label>
                            <input type="number" id="y_area" value="2.5" step="0.1" min="0.1">
                        </div>
                        <div class="form-group">
                            <label for="y_variety">Crop Variety</label>
                            <select id="y_variety">
                                <option value="Standard">Standard</option>
                                <option value="High-yielding">High-yielding</option>
                                <option value="Drought-resistant">Drought-resistant</option>
                                <option value="Disease-resistant">Disease-resistant</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="form-section">
                        <h4><i class="fas fa-tractor"></i> Management Practices</h4>
                        <div class="form-group">
                            <label for="y_irrigation">Irrigation Type</label>
                            <select id="y_irrigation">
                                <option value="Rainfed">Rainfed</option>
                                <option value="Flood">Flood Irrigation</option>
                                <option value="Drip">Drip Irrigation</option>
                                <option value="Sprinkler">Sprinkler</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="y_fertilizer">Fertilizer Level</label>
                            <select id="y_fertilizer">
                                <option value="Low">Low</option>
                                <option value="Moderate">Moderate</option>
                                <option value="High">High</option>
                                <option value="Precision">Precision Application</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <button type="button" class="btn-primary" onclick="getYieldPrediction()">
                    <i class="fas fa-chart-line"></i> Predict Yield
                </button>
            </div>

            <div id="yieldLoading" class="loading hidden">
                <div class="spinner"></div>
                <p>Running AI prediction models...</p>
            </div>

            <div id="yieldResult" class="result-card hidden">
                <h3><i class="fas fa-chart-line"></i> Yield Prediction Results</h3>
                <div id="yieldPredictions"></div>
            </div>
        </section>

        <!-- Weather Section -->
        <section id="weather" class="section hidden">
            <div class="form-container">
                <h2><i class="fas fa-cloud-sun"></i> Agricultural Weather Station</h2>
                
                <div class="form-group">
                    <label for="location">Enter Location</label>
                    <input type="text" id="location" placeholder="City, Country" value="New York, US">
                </div>
                <button type="button" class="btn-primary" onclick="getWeatherData()">
                    <i class="fas fa-search"></i> Get Weather Data
                </button>
            </div>

            <div id="weatherLoading" class="loading hidden">
                <div class="spinner"></div>
                <p>Fetching weather data...</p>
            </div>

            <div id="weatherResult" class="result-card hidden">
                <h3><i class="fas fa-cloud-sun"></i> Weather Analysis</h3>
                <div id="weatherData"></div>
            </div>
        </section>

        <!-- Disease Detection Section -->
        <section id="disease-detection" class="section hidden">
            <div class="form-container">
                <h2><i class="fas fa-bug"></i> AI-Powered Crop Disease Detection</h2>
                <p>Upload a photo of your crop leaves for instant disease diagnosis and treatment recommendations.</p>
                
                <div class="form-group">
                    <label for="disease-crop-type">Select Crop Type</label>
                    <select id="disease-crop-type">
                        <option value="">Select Crop</option>
                        <option value="Tomato">Tomato</option>
                        <option value="Potato">Potato</option>
                        <option value="Corn">Corn</option>
                        <option value="Rice">Rice</option>
                    </select>
                </div>
                
                <div class="upload-area" id="uploadArea">
                    <input type="file" id="fileInput" accept="image/*" style="display: none;">
                    <i class="fas fa-cloud-upload-alt" style="font-size: 3rem; color: #667eea; margin-bottom: 1rem;"></i>
                    <p>Click to upload an image or drag and drop</p>
                    <p style="font-size: 0.8rem; color: #666;">Supported formats: JPG, PNG, JPEG | Max size: 5MB</p>
                </div>
                
                <img id="imagePreview" class="image-preview" alt="Image preview">
                
                <button type="button" class="btn-primary" id="analyzeBtn" disabled onclick="analyzeImage()">
                    <i class="fas fa-search"></i> Analyze Image
                </button>
            </div>

            <div id="diseaseLoading" class="loading hidden">
                <div class="spinner"></div>
                <p>Analyzing image for disease patterns...</p>
            </div>

            <div id="diseaseResult" class="result-card hidden">
                <h3><i class="fas fa-bug"></i> Disease Analysis Results</h3>
                <div id="diseaseAnalysis"></div>
            </div>
        </section>

        <!-- Market Helper Section -->
        <section id="market-helper" class="section hidden">
            <div class="form-container">
                <div class="mb-6 flex items-center space-x-2" style="margin-bottom: 1.5rem; display: flex; gap: 0.5rem;">
                    <input type="text" id="voiceInput" placeholder="Search markets, equipment, laborers..." style="flex: 1; padding: 0.5rem; border: 1px solid #ccc; border-radius: 8px;">
                    <button id="searchBtn" class="btn-primary" onclick="handleMarketSearch()" style="margin: 0; padding: 0.5rem 1rem;">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
                
                <!-- Market Helper Home -->
                <div id="marketHome">
                    <div class="gradient-bg p-8 rounded-xl text-white text-center" style="padding: 2rem; border-radius: 12px; margin-bottom: 2rem;">
                        <h1 style="font-size: 2rem; margin-bottom: 1rem;">Smart Farming Companion</h1>
                        <p style="font-size: 1.1rem; opacity: 0.9;">Market prices, equipment, laborers, and government schemes</p>
                    </div>
                    
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1rem; margin-bottom: 2rem;">
                        <div class="card" onclick="showMarketSection('prices')" style="background: white; padding: 1.5rem; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); border-left: 4px solid #10b981;">
                            <i class="fas fa-chart-line" style="font-size: 2.5rem; color: #10b981; margin-bottom: 1rem;"></i>
                            <h3 style="color: #1f2937; margin-bottom: 0.5rem;">Market Prices</h3>
                            <p style="color: #6b7280; font-size: 0.9rem;">Real-time pricing</p>
                        </div>
                        
                        <div class="card" onclick="showMarketSection('laborers')" style="background: white; padding: 1.5rem; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); border-left: 4px solid #f59e0b;">
                            <i class="fas fa-users" style="font-size: 2.5rem; color: #f59e0b; margin-bottom: 1rem;"></i>
                            <h3 style="color: #1f2937; margin-bottom: 0.5rem;">Laborers</h3>
                            <p style="color: #6b7280; font-size: 0.9rem;">Available workers</p>
                        </div>
                        
                        <div class="card" onclick="showMarketSection('equipment')" style="background: white; padding: 1.5rem; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); border-left: 4px solid #8b5cf6;">
                            <i class="fas fa-tractor" style="font-size: 2.5rem; color: #8b5cf6; margin-bottom: 1rem;"></i>
                            <h3 style="color: #1f2937; margin-bottom: 0.5rem;">Equipment</h3>
                            <p style="color: #6b7280; font-size: 0.9rem;">Rental services</p>
                        </div>
                        
                        <div class="card" onclick="showMarketSection('shops')" style="background: white; padding: 1.5rem; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); border-left: 4px solid #06b6d4;">
                            <i class="fas fa-store" style="font-size: 2.5rem; color: #06b6d4; margin-bottom: 1rem;"></i>
                            <h3 style="color: #1f2937; margin-bottom: 0.5rem;">Agri Shops</h3>
                            <p style="color: #6b7280; font-size: 0.9rem;">Seeds & supplies</p>
                        </div>
                    </div>
                    
                    <div class="card" onclick="showMarketSection('schemes')" style="background: linear-gradient(135deg, #f59e0b 0%, #ef4444 100%); color: white; padding: 2rem; border-radius: 12px; text-align: center; cursor: pointer;">
                        <i class="fas fa-landmark" style="font-size: 2rem; margin-bottom: 1rem;"></i>
                        <h3 style="font-size: 1.2rem; margin: 0;">Government Schemes</h3>
                    </div>
                </div>

                <!-- Market Prices Section -->
                <div id="marketPrices" class="hidden">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem;">
                        <h2 style="color: #1f2937; font-size: 1.5rem; margin: 0;">Market Prices</h2>
                        <button onclick="showMarketSection('home')" class="btn-primary" style="margin: 0; padding: 0.5rem 1rem;">
                            <i class="fas fa-arrow-left"></i> Back
                        </button>
                    </div>
                    <div id="pricesList">
                        <!-- Prices will be populated here -->
                    </div>
                </div>

                <!-- Laborers Section -->
                <div id="marketLaborers" class="hidden">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem;">
                        <h2 style="color: #1f2937; font-size: 1.5rem; margin: 0;">Available Laborers</h2>
                        <button onclick="showMarketSection('home')" class="btn-primary" style="margin: 0; padding: 0.5rem 1rem;">
                            <i class="fas fa-arrow-left"></i> Back
                        </button>
                    </div>
                    <div id="laborersList">
                        <!-- Laborers will be populated here -->
                    </div>
                </div>

                <!-- Equipment Section -->
                <div id="marketEquipment" class="hidden">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem;">
                        <h2 style="color: #1f2937; font-size: 1.5rem; margin: 0;">Equipment Rental</h2>
                        <button onclick="showMarketSection('home')" class="btn-primary" style="margin: 0; padding: 0.5rem 1rem;">
                            <i class="fas fa-arrow-left"></i> Back
                        </button>
                    </div>
                    <div id="equipmentList">
                        <!-- Equipment will be populated here -->
                    </div>
                </div>

                <!-- Shops Section -->
                <div id="marketShops" class="hidden">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem;">
                        <h2 style="color: #1f2937; font-size: 1.5rem; margin: 0;">Agricultural Shops</h2>
                        <button onclick="showMarketSection('home')" class="btn-primary" style="margin: 0; padding: 0.5rem 1rem;">
                            <i class="fas fa-arrow-left"></i> Back
                        </button>
                    </div>
                    <div id="shopsList">
                        <!-- Shops will be populated here -->
                    </div>
                </div>

                <!-- Government Schemes Section -->
                <div id="marketSchemes" class="hidden">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem;">
                        <h2 style="color: #1f2937; font-size: 1.5rem; margin: 0;">Government Schemes</h2>
                        <button onclick="showMarketSection('home')" class="btn-primary" style="margin: 0; padding: 0.5rem 1rem;">
                            <i class="fas fa-arrow-left"></i> Back
                        </button>
                    </div>
                    <div id="schemesList">
                        <!-- Schemes will be populated here -->
                    </div>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Data and state management
        let currentSection = 'home';
        let currentMarketSection = 'home';

        // Crop database
        const cropDatabase = {
            Rice: { ph: { min: 5.5, max: 7.0, optimal: 6.0 }, temperature: { min: 20, max: 35, optimal: 25 }, 
                   rainfall: { min: 1000, max: 2000, optimal: 1200 }, nitrogen: { min: 40, max: 80, optimal: 60 },
                   phosphorous: { min: 10, max: 25, optimal: 18 }, potassium: { min: 20, max: 40, optimal: 30 },
                   humidity: { min: 60, max: 85, optimal: 70 }, yield: { min: 3, max: 8, optimal: 5.5 },
                   growthPeriod: 120, region: ['Tropical', 'Subtropical'] },
            Wheat: { ph: { min: 6.0, max: 7.5, optimal: 6.8 }, temperature: { min: 15, max: 25, optimal: 20 },
                    rainfall: { min: 350, max: 700, optimal: 500 }, nitrogen: { min: 80, max: 120, optimal: 100 },
                    phosphorous: { min: 20, max: 40, optimal: 30 }, potassium: { min: 25, max: 50, optimal: 35 },
                    humidity: { min: 50, max: 70, optimal: 60 }, yield: { min: 2, max: 6, optimal: 4 },
                    growthPeriod: 90, region: ['Temperate', 'Subtropical'] },
            Corn: { ph: { min: 6.0, max: 7.0, optimal: 6.5 }, temperature: { min: 18, max: 30, optimal: 24 },
                   rainfall: { min: 500, max: 1200, optimal: 800 }, nitrogen: { min: 120, max: 200, optimal: 160 },
                   phosphorous: { min: 25, max: 50, optimal: 35 }, potassium: { min: 100, max: 180, optimal: 140 },
                   humidity: { min: 55, max: 75, optimal: 65 }, yield: { min: 4, max: 12, optimal: 8 },
                   growthPeriod: 110, region: ['Temperate', 'Subtropical', 'Tropical'] },
            Tomato: { ph: { min: 6.0, max: 7.0, optimal: 6.5 }, temperature: { min: 18, max: 28, optimal: 23 },
                     rainfall: { min: 400, max: 800, optimal: 600 }, nitrogen: { min: 150, max: 250, optimal: 200 },
                     phosphorous: { min: 30, max: 60, optimal: 45 }, potassium: { min: 200, max: 350, optimal: 275 },
                     humidity: { min: 60, max: 80, optimal: 70 }, yield: { min: 20, max: 80, optimal: 50 },
                     growthPeriod: 90, region: ['Temperate', 'Subtropical', 'Tropical'] },
            Potato: { ph: { min: 4.8, max: 6.5, optimal: 5.8 }, temperature: { min: 15, max: 22, optimal: 18 },
                     rainfall: { min: 400, max: 700, optimal: 550 }, nitrogen: { min: 120, max: 180, optimal: 150 },
                     phosphorous: { min: 40, max: 80, optimal: 60 }, potassium: { min: 200, max: 350, optimal: 275 },
                     humidity: { min: 70, max: 90, optimal: 80 }, yield: { min: 15, max: 50, optimal: 32 },
                     growthPeriod: 75, region: ['Temperate'] }
        };

        // Fertilizer database
        const fertilizerDatabase = {
            Rice: { N: 120, P: 60, K: 40 }, Wheat: { N: 120, P: 60, K: 40 },
            Corn: { N: 180, P: 80, K: 60 }, Tomato: { N: 200, P: 100, K: 250 },
            Potato: { N: 150, P: 120, K: 200 }
        };

        // Market data
        const marketData = {
            prices: [
                { name: "Rice", price: 45, unit: "kg", change: "+2%", trend: "up" },
                { name: "Wheat", price: 35, unit: "kg", change: "-1%", trend: "down" },
                { name: "Tomato", price: 25, unit: "kg", change: "+5%", trend: "up" },
                { name: "Onion", price: 30, unit: "kg", change: "+3%", trend: "up" },
                { name: "Potato", price: 28, unit: "kg", change: "-2%", trend: "down" }
            ],
            laborers: [
                { name: "Rajesh Kumar", specialty: "Harvesting", rate: 400, unit: "day", contact: "9876543210", rating: 4.2, available: true },
                { name: "Suresh Patel", specialty: "Plowing", rate: 350, unit: "day", contact: "8765432109", rating: 3.8, available: true },
                { name: "Mohan Singh", specialty: "Planting", rate: 300, unit: "day", contact: "7654321098", rating: 4.5, available: false },
                { name: "Ramesh Yadav", specialty: "Irrigation", rate: 450, unit: "day", contact: "6543210987", rating: 4.0, available: true }
            ],
            equipment: [
                { name: "Tractor", price: 1500, unit: "day", contact: "FarmTech Solutions", rating: 4.3, available: true },
                { name: "Harvester", price: 2500, unit: "day", contact: "AgriMachinery Ltd", rating: 4.5, available: true },
                { name: "Seed Drill", price: 800, unit: "day", contact: "Modern Farm Equipment", rating: 4.1, available: false },
                { name: "Sprayer", price: 600, unit: "day", contact: "Crop Care Services", rating: 3.9, available: true }
            ],
            shops: [
                { name: "Green Fields Seeds", type: "Seeds", contact: "9876543210", location: "Main Market", rating: 4.3 },
                { name: "Organic Farm Solutions", type: "Organic Fertilizers", contact: "8765432109", location: "Agriculture Hub", rating: 4.5 },
                { name: "AgriChem Industries", type: "Pesticides", contact: "7654321098", location: "Industrial Area", rating: 4.0 },
                { name: "Farm Tools & Equipment", type: "Tools", contact: "6543210987", location: "Equipment Market", rating: 4.2 }
            ],
            schemes: [
                { name: "PM-KISAN Scheme", amount: "₹6,000/year", eligibility: "Small & marginal farmers", 
                  description: "Direct income support to farmers" },
                { name: "Crop Insurance Scheme", amount: "Premium subsidy up to 90%", eligibility: "All farmers", 
                  description: "Protection against crop losses" },
                { name: "Soil Health Card Scheme", amount: "Free testing", eligibility: "All farmers", 
                  description: "Soil nutrient status and recommendations" },
                { name: "Drip Irrigation Subsidy", amount: "Up to 55% subsidy", eligibility: "Farmers with 0.5+ acres", 
                  description: "Water-efficient irrigation systems" }
            ]
        };

        // Disease database
        const diseaseDatabase = {
            Tomato: {
                "Early Blight": {
                    symptoms: ["Dark spots with concentric rings on leaves", "Yellowing around spots"],
                    causes: "Fungal infection (Alternaria solani)",
                    treatment: ["Remove infected plant parts", "Apply copper-based fungicides", "Use neem oil"],
                    prevention: ["Practice crop rotation", "Ensure proper spacing", "Water at the base"]
                },
                "Healthy": {
                    symptoms: ["No visible spots or lesions", "Vibrant green color"],
                    causes: "No disease detected",
                    treatment: ["Maintain current practices"],
                    prevention: ["Continue good cultural practices", "Regular monitoring"]
                }
            },
            Potato: {
                "Late Blight": {
                    symptoms: ["Dark water-soaked spots", "White fungal growth"],
                    causes: "Phytophthora infestans infection",
                    treatment: ["Apply fungicides with mancozeb", "Remove infected plants"],
                    prevention: ["Plant certified seed potatoes", "Improve drainage"]
                },
                "Healthy": {
                    symptoms: ["No lesions or spots", "Normal growth"],
                    causes: "No disease detected",
                    treatment: ["Continue current management"],
                    prevention: ["Maintain proper practices"]
                }
            }
        };

        // Main functions
        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.classList.add('hidden');
            });
            document.getElementById(sectionId).classList.remove('hidden');
            currentSection = sectionId;
            
            if (sectionId === 'home') {
                updateSensorData();
            } else if (sectionId === 'market-helper') {
                showMarketSection('home');
            }
        }

        function showMarketSection(section) {
            const sections = ['marketHome', 'marketPrices', 'marketLaborers', 'marketEquipment', 'marketShops', 'marketSchemes'];
            sections.forEach(s => {
                const el = document.getElementById(s);
                if (el) el.classList.add('hidden');
            });
            
            currentMarketSection = section;
            
            if (section === 'home') {
                document.getElementById('marketHome').classList.remove('hidden');
            } else if (section === 'prices') {
                document.getElementById('marketPrices').classList.remove('hidden');
                displayMarketPrices();
            } else if (section === 'laborers') {
                document.getElementById('marketLaborers').classList.remove('hidden');
                displayLaborers();
            } else if (section === 'equipment') {
                document.getElementById('marketEquipment').classList.remove('hidden');
                displayEquipment();
            } else if (section === 'shops') {
                document.getElementById('marketShops').classList.remove('hidden');
                displayShops();
            } else if (section === 'schemes') {
                document.getElementById('marketSchemes').classList.remove('hidden');
                displaySchemes();
            }
        }

        function updateSensorData() {
            const sensors = [
                { label: 'Soil Moisture', value: Math.round(55 + Math.random() * 20) + '%', status: 'normal', icon: 'fas fa-tint' },
                { label: 'Temperature', value: (22 + Math.random() * 6).toFixed(1) + '°C', status: 'normal', icon: 'fas fa-thermometer-half' },
                { label: 'Humidity', value: Math.round(60 + Math.random() * 20) + '%', status: 'normal', icon: 'fas fa-cloud' },
                { label: 'Nitrogen', value: Math.round(30 + Math.random() * 20) + ' ppm', status: 'warning', icon: 'fas fa-leaf' },
                { label: 'pH Level', value: (6.2 + Math.random() * 0.8).toFixed(1), status: 'normal', icon: 'fas fa-vial' },
                { label: 'Light', value: Math.round(800 + Math.random() * 400) + ' lux', status: 'normal', icon: 'fas fa-sun' }
            ];

            const container = document.getElementById('liveSensorData');
            container.innerHTML = sensors.map(sensor => `
                <div class="sensor-card">
                    <div class="sensor-label"><i class="${sensor.icon}"></i> ${sensor.label}</div>
                    <div class="sensor-value">${sensor.value}</div>
                    <div class="sensor-status status-${sensor.status}">${sensor.status === 'normal' ? 'Optimal' : 'Monitor'}</div>
                </div>
            `).join('');
        }

        function calculateSuitability(crop, inputs) {
            const cropData = cropDatabase[crop];
            if (!cropData) return 0;
            
            let score = 0;
            let factors = 0;

            // pH suitability
            const phDiff = Math.abs(inputs.ph - cropData.ph.optimal);
            score += Math.max(0, 20 - phDiff * 5);
            factors += 20;

            // Temperature suitability
            const tempDiff = Math.abs(inputs.temperature - cropData.temperature.optimal);
            score += Math.max(0, 20 - tempDiff * 2);
            factors += 20;

            // Rainfall suitability
            const rainDiff = Math.abs(inputs.rainfall - cropData.rainfall.optimal);
            score += Math.max(0, 15 - rainDiff / 100);
            factors += 15;

            // Nutrient suitability
            const nScore = Math.max(0, 15 - Math.abs(inputs.nitrogen - cropData.nitrogen.optimal) / 5);
            const pScore = Math.max(0, 15 - Math.abs(inputs.phosphorous - cropData.phosphorous.optimal) / 3);
            const kScore = Math.max(0, 15 - Math.abs(inputs.potassium - cropData.potassium.optimal) / 10);
            score += (nScore + pScore + kScore) / 3;
            factors += 15;

            // Region suitability
            if (cropData.region.includes(inputs.region)) {
                score += 10;
            }
            factors += 10;

            return Math.round((score / factors) * 100);
        }

        function getCropRecommendation() {
            const inputs = {
                nitrogen: parseFloat(document.getElementById('nitrogen').value),
                phosphorous: parseFloat(document.getElementById('phosphorous').value),
                potassium: parseFloat(document.getElementById('potassium').value),
                ph: parseFloat(document.getElementById('ph').value),
                temperature: parseFloat(document.getElementById('temperature').value),
                rainfall: parseFloat(document.getElementById('rainfall').value),
                humidity: parseFloat(document.getElementById('humidity').value),
                region: document.getElementById('region').value,
                soil_type: document.getElementById('soil_type').value
            };

            document.getElementById('cropLoading').classList.remove('hidden');
            document.getElementById('cropResult').classList.add('hidden');

            setTimeout(() => {
                const recommendations = [];
                
                for (const [crop, data] of Object.entries(cropDatabase)) {
                    const suitability = calculateSuitability(crop, inputs);
                    recommendations.push({ crop: crop, suitability: suitability, data: data });
                }

                recommendations.sort((a, b) => b.suitability - a.suitability);
                displayCropRecommendations(recommendations.slice(0, 5), inputs);
                
                document.getElementById('cropLoading').classList.add('hidden');
                document.getElementById('cropResult').classList.remove('hidden');
            }, 2000);
        }

        function displayCropRecommendations(recommendations, inputs) {
            const container = document.getElementById('cropRecommendations');
            
            container.innerHTML = recommendations.map((rec, index) => {
                const confidenceClass = rec.suitability >= 80 ? 'high-confidence' : 
                                      rec.suitability >= 60 ? 'medium-confidence' : 'low-confidence';
                
                return `
                    <div style="background: white; border-radius: 8px; padding: 1rem; margin: 1rem 0; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
                        <h4>${index + 1}. ${rec.crop} <span class="confidence-level ${confidenceClass}">${rec.suitability}% Match</span></h4>
                        <p>Expected yield: ${rec.data.yield.min}-${rec.data.yield.max} tons/ha (Optimal: ${rec.data.yield.optimal} tons/ha)</p>
                        <div class="confidence-bar">
                            <div class="confidence-fill" style="width: ${rec.suitability}%"></div>
                        </div>
                        <div class="recommendation-item">
                            <strong>Growth Requirements:</strong>
                            <ul>
                                <li>pH Range: ${rec.data.ph.min} - ${rec.data.ph.max} (Your soil: ${inputs.ph})</li>
                                <li>Temperature: ${rec.data.temperature.min}°C - ${rec.data.temperature.max}°C (Current: ${inputs.temperature}°C)</li>
                                <li>Water needs: ${rec.data.rainfall.min}-${rec.data.rainfall.max}mm (Available: ${inputs.rainfall}mm)</li>
                                <li>Growing period: ${rec.data.growthPeriod} days</li>
                            </ul>
                        </div>
                    </div>
                `;
            }).join('');
        }

        function getFertilizerRecommendation() {
            const crop = document.getElementById('f_crop_type').value;
            if (!crop) {
                alert('Please select a crop type');
                return;
            }

            const area = parseFloat(document.getElementById('f_area').value);
            const currentN = parseFloat(document.getElementById('f_nitrogen').value);
            const currentP = parseFloat(document.getElementById('f_phosphorous').value);
            const currentK = parseFloat(document.getElementById('f_potassium').value);

            document.getElementById('fertilizerLoading').classList.remove('hidden');
            document.getElementById('fertilizerResult').classList.add('hidden');

            setTimeout(() => {
                const requirements = fertilizerDatabase[crop];
                const recommendation = {
                    nDeficit: Math.max(0, (requirements.N - currentN) * area),
                    pDeficit: Math.max(0, (requirements.P - currentP) * area),
                    kDeficit: Math.max(0, (requirements.K - currentK) * area)
                };
                
                recommendation.urea = Math.round(recommendation.nDeficit / 0.46);
                recommendation.dap = Math.round(recommendation.pDeficit / 0.46);
                recommendation.mop = Math.round(recommendation.kDeficit / 0.60);
                recommendation.totalCost = Math.round(recommendation.urea * 0.45 + recommendation.dap * 0.55 + recommendation.mop * 0.40);

                displayFertilizerRecommendation(recommendation);
                
                document.getElementById('fertilizerLoading').classList.add('hidden');
                document.getElementById('fertilizerResult').classList.remove('hidden');
            }, 1500);
        }

        function displayFertilizerRecommendation(rec) {
            document.getElementById('fertilizerRecommendations').innerHTML = `
                <div class="data-grid">
                    <div class="data-item">
                        <h5>Nitrogen Needed</h5>
                        <p>${Math.round(rec.nDeficit)} kg</p>
                    </div>
                    <div class="data-item">
                        <h5>Phosphorus Needed</h5>
                        <p>${Math.round(rec.pDeficit)} kg</p>
                    </div>
                    <div class="data-item">
                        <h5>Potassium Needed</h5>
                        <p>${Math.round(rec.kDeficit)} kg</p>
                    </div>
                    <div class="data-item">
                        <h5>Estimated Cost</h5>
                        <p>${rec.totalCost}</p>
                    </div>
                </div>
                <div class="recommendation-item">
                    <h4>Fertilizer Recommendations</h4>
                    <p><strong>Urea (46-0-0):</strong> ${rec.urea} kg - Apply in 2-3 splits</p>
                    <p><strong>DAP (18-46-0):</strong> ${rec.dap} kg - Apply at planting</p>
                    <p><strong>MOP (0-0-60):</strong> ${rec.mop} kg - Apply at planting</p>
                </div>
            `;
        }

        function getYieldPrediction() {
            const crop = document.getElementById('y_crop').value;
            if (!crop) {
                alert('Please select a crop type');
                return;
            }

            document.getElementById('yieldLoading').classList.remove('hidden');
            document.getElementById('yieldResult').classList.add('hidden');

            setTimeout(() => {
                const area = parseFloat(document.getElementById('y_area').value);
                const variety = document.getElementById('y_variety').value;
                const irrigation = document.getElementById('y_irrigation').value;
                const fertilizer = document.getElementById('y_fertilizer').value;

                const baseYield = cropDatabase[crop].yield.optimal;
                let multiplier = 1.0;

                // Apply variety multiplier
                const varietyMultipliers = { 'Standard': 1.0, 'High-yielding': 1.25, 'Drought-resistant': 0.95, 'Disease-resistant': 1.1 };
                multiplier *= varietyMultipliers[variety] || 1.0;

                // Apply irrigation multiplier
                const irrigationMultipliers = { 'Rainfed': 0.8, 'Flood': 1.0, 'Drip': 1.2, 'Sprinkler': 1.1 };
                multiplier *= irrigationMultipliers[irrigation] || 1.0;

                // Apply fertilizer multiplier
                const fertilizerMultipliers = { 'Low': 0.7, 'Moderate': 1.0, 'High': 1.15, 'Precision': 1.3 };
                multiplier *= fertilizerMultipliers[fertilizer] || 1.0;

                const predictedYield = baseYield * multiplier;
                const totalProduction = predictedYield * area;

                document.getElementById('yieldPredictions').innerHTML = `
                    <div class="data-grid">
                        <div class="data-item">
                            <h5>Predicted Yield</h5>
                            <p>${predictedYield.toFixed(2)} tons/ha</p>
                        </div>
                        <div class="data-item">
                            <h5>Total Production</h5>
                            <p>${totalProduction.toFixed(2)} tons</p>
                        </div>
                        <div class="data-item">
                            <h5>Confidence</h5>
                            <p>85%</p>
                        </div>
                        <div class="data-item">
                            <h5>Risk Level</h5>
                            <p>Low</p>
                        </div>
                    </div>
                    <div class="recommendation-item">
                        <h4>Factors Affecting Yield</h4>
                        <p><strong>Variety Impact:</strong> ${((varietyMultipliers[variety] - 1) * 100).toFixed(1)}%</p>
                        <p><strong>Irrigation Impact:</strong> ${((irrigationMultipliers[irrigation] - 1) * 100).toFixed(1)}%</p>
                        <p><strong>Fertilizer Impact:</strong> ${((fertilizerMultipliers[fertilizer] - 1) * 100).toFixed(1)}%</p>
                    </div>
                `;
                
                document.getElementById('yieldLoading').classList.add('hidden');
                document.getElementById('yieldResult').classList.remove('hidden');
            }, 2500);
        }

        function getWeatherData() {
            const location = document.getElementById('location').value;
            if (!location) {
                alert('Please enter a location');
                return;
            }

            document.getElementById('weatherLoading').classList.remove('hidden');
            document.getElementById('weatherResult').classList.add('hidden');

            setTimeout(() => {
                const mockData = {
                    current: {
                        temperature: Math.round(20 + Math.random() * 15),
                        humidity: Math.round(50 + Math.random() * 30),
                        windSpeed: Math.round(5 + Math.random() * 10),
                        condition: ['Sunny', 'Partly Cloudy', 'Cloudy', 'Light Rain'][Math.floor(Math.random() * 4)]
                    },
                    forecast: Array.from({length: 7}, (_, i) => ({
                        day: new Date(Date.now() + i * 24 * 60 * 60 * 1000).toLocaleDateString('en-US', {weekday: 'short'}),
                        temperature: Math.round(18 + Math.random() * 12),
                        condition: ['Sunny', 'Cloudy', 'Rain'][Math.floor(Math.random() * 3)]
                    }))
                };

                document.getElementById('weatherData').innerHTML = `
                    <div class="data-grid">
                        <div class="data-item">
                            <h5>Temperature</h5>
                            <p>${mockData.current.temperature}°C</p>
                        </div>
                        <div class="data-item">
                            <h5>Humidity</h5>
                            <p>${mockData.current.humidity}%</p>
                        </div>
                        <div class="data-item">
                            <h5>Wind Speed</h5>
                            <p>${mockData.current.windSpeed} km/h</p>
                        </div>
                        <div class="data-item">
                            <h5>Condition</h5>
                            <p>${mockData.current.condition}</p>
                        </div>
                    </div>
                    <div class="recommendation-item">
                        <h4>7-Day Forecast for ${location}</h4>
                        <div class="data-grid">
                            ${mockData.forecast.map(day => `
                                <div class="data-item">
                                    <h5>${day.day}</h5>
                                    <p>${day.temperature}°C</p>
                                    <p>${day.condition}</p>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                    <div class="recommendation-item">
                        <h4>Agricultural Advisory</h4>
                        <p><i class="fas fa-info-circle"></i> Current conditions are suitable for most farming operations.</p>
                        <p><i class="fas fa-lightbulb"></i> Consider irrigation if dry conditions persist.</p>
                    </div>
                `;
                
                document.getElementById('weatherLoading').classList.add('hidden');
                document.getElementById('weatherResult').classList.remove('hidden');
            }, 1500);
        }

        function analyzeImage() {
            const cropType = document.getElementById('disease-crop-type').value;
            if (!cropType) {
                alert('Please select a crop type');
                return;
            }

            document.getElementById('diseaseLoading').classList.remove('hidden');
            document.getElementById('diseaseResult').classList.add('hidden');

            setTimeout(() => {
                const diseases = diseaseDatabase[cropType];
                const diseaseKeys = Object.keys(diseases);
                const randomDisease = diseaseKeys[Math.floor(Math.random() * diseaseKeys.length)];
                const diseaseInfo = diseases[randomDisease];
                const confidence = Math.round(60 + Math.random() * 30);

                document.getElementById('diseaseAnalysis').innerHTML = `
                    <div style="background: white; border-radius: 8px; padding: 1rem; margin: 1rem 0;">
                        <div style="font-weight: bold; color: #667eea; margin-bottom: 0.5rem;">
                            ${randomDisease} 
                            <span class="confidence-level ${confidence >= 80 ? 'high-confidence' : confidence >= 60 ? 'medium-confidence' : 'low-confidence'}">${confidence}% confidence</span>
                        </div>
                        
                        ${randomDisease !== 'Healthy' ? `
                            <p><strong>Symptoms:</strong> ${diseaseInfo.symptoms.join(', ')}</p>
                            <p><strong>Causes:</strong> ${diseaseInfo.causes}</p>
                            
                            <div class="recommendation-item">
                                <strong>Treatment:</strong>
                                <ul>
                                    ${diseaseInfo.treatment.map(item => `<li>${item}</li>`).join('')}
                                </ul>
                            </div>
                            
                            <div class="recommendation-item">
                                <strong>Prevention:</strong>
                                <ul>
                                    ${diseaseInfo.prevention.map(item => `<li>${item}</li>`).join('')}
                                </ul>
                            </div>
                        ` : `
                            <p>Your ${cropType} plant appears healthy with no signs of disease.</p>
                            <div class="recommendation-item">
                                <strong>Maintenance:</strong>
                                <ul>
                                    ${diseaseInfo.prevention.map(item => `<li>${item}</li>`).join('')}
                                </ul>
                            </div>
                        `}
                    </div>
                `;
                
                document.getElementById('diseaseLoading').classList.add('hidden');
                document.getElementById('diseaseResult').classList.remove('hidden');
            }, 2500);
        }

        // Market helper functions
        function displayMarketPrices() {
            const container = document.getElementById('pricesList');
            container.innerHTML = marketData.prices.map(item => `
                <div style="background: white; padding: 1rem; border-radius: 8px; margin-bottom: 1rem; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-left: 4px solid #10b981;">
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <h3 style="margin: 0; color: #1f2937;">${item.name}</h3>
                        <span style="color: ${item.trend === 'up' ? '#10b981' : '#ef4444'}; font-weight: bold;">${item.change}</span>
                    </div>
                    <div style="margin-top: 0.5rem; display: flex; justify-content: space-between; align-items: center;">
                        <span style="color: #6b7280;">Price</span>
                        <span style="font-weight: bold; color: #1f2937;">₹${item.price}/${item.unit}</span>
                    </div>
                </div>
            `).join('');
        }

        function displayLaborers() {
            const container = document.getElementById('laborersList');
            container.innerHTML = marketData.laborers.map(laborer => `
                <div style="background: white; padding: 1rem; border-radius: 8px; margin-bottom: 1rem; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-left: 4px solid #f59e0b;">
                    <div style="display: flex; justify-content: space-between; align-items: start; margin-bottom: 0.5rem;">
                        <div>
                            <h3 style="margin: 0; color: #1f2937;">${laborer.name}</h3>
                            <p style="margin: 0.25rem 0; color: #6b7280; font-size: 0.9rem;">${laborer.specialty}</p>
                        </div>
                        <div style="display: flex; align-items: center;">
                            <i class="fas fa-star" style="color: #f59e0b; margin-right: 0.25rem;"></i>
                            <span style="color: #6b7280;">${laborer.rating}</span>
                        </div>
                    </div>
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 0.5rem;">
                        <span style="color: ${laborer.available ? '#10b981' : '#ef4444'}; font-size: 0.9rem;">
                            ${laborer.available ? 'Available' : 'Busy'}
                        </span>
                        <span style="font-weight: bold;">₹${laborer.rate}/${laborer.unit}</span>
                    </div>
                    <div style="display: flex; justify-content: space-between; align-items: center;">
                        <span style="color: #6b7280; font-size: 0.9rem;">${laborer.contact}</span>
                        <button style="background: #10b981; color: white; padding: 0.25rem 0.75rem; border: none; border-radius: 4px; font-size: 0.8rem; cursor: pointer;">
                            Call Now
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function displayEquipment() {
            const container = document.getElementById('equipmentList');
            container.innerHTML = marketData.equipment.map(equipment => `
                <div style="background: white; padding: 1rem; border-radius: 8px; margin-bottom: 1rem; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-left: 4px solid #8b5cf6;">
                    <div style="display: flex; justify-content: space-between; align-items: start; margin-bottom: 0.5rem;">
                        <div>
                            <h3 style="margin: 0; color: #1f2937;">${equipment.name}</h3>
                            <p style="margin: 0.25rem 0; color: #6b7280; font-size: 0.9rem;">${equipment.contact}</p>
                        </div>
                        <div style="display: flex; align-items: center;">
                            <i class="fas fa-star" style="color: #f59e0b; margin-right: 0.25rem;"></i>
                            <span style="color: #6b7280;">${equipment.rating}</span>
                        </div>
                    </div>
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 0.5rem;">
                        <span style="color: ${equipment.available ? '#10b981' : '#ef4444'}; font-size: 0.9rem;">
                            ${equipment.available ? 'Available' : 'Busy'}
                        </span>
                        <span style="font-weight: bold;">₹${equipment.price}/${equipment.unit}</span>
                    </div>
                    <div style="text-align: right;">
                        <button style="background: #8b5cf6; color: white; padding: 0.25rem 0.75rem; border: none; border-radius: 4px; font-size: 0.8rem; cursor: pointer;">
                            Book Now
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function displayShops() {
            const container = document.getElementById('shopsList');
            container.innerHTML = marketData.shops.map(shop => `
                <div style="background: white; padding: 1rem; border-radius: 8px; margin-bottom: 1rem; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-left: 4px solid #06b6d4;">
                    <div style="display: flex; justify-content: space-between; align-items: start; margin-bottom: 0.5rem;">
                        <div>
                            <h3 style="margin: 0; color: #1f2937;">${shop.name}</h3>
                            <p style="margin: 0.25rem 0; color: #6b7280; font-size: 0.9rem;">${shop.type}</p>
                        </div>
                        <div style="display: flex; align-items: center;">
                            <i class="fas fa-star" style="color: #f59e0b; margin-right: 0.25rem;"></i>
                            <span style="color: #6b7280;">${shop.rating}</span>
                        </div>
                    </div>
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 0.5rem;">
                        <span style="color: #6b7280; font-size: 0.9rem;">
                            <i class="fas fa-map-marker-alt"></i> ${shop.location}
                        </span>
                        <span style="color: #6b7280; font-size: 0.9rem;">${shop.contact}</span>
                    </div>
                    <div style="text-align: right;">
                        <button style="background: #06b6d4; color: white; padding: 0.25rem 0.75rem; border: none; border-radius: 4px; font-size: 0.8rem; cursor: pointer;">
                            Visit Shop
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function displaySchemes() {
            const container = document.getElementById('schemesList');
            container.innerHTML = marketData.schemes.map(scheme => `
                <div style="background: white; padding: 1rem; border-radius: 8px; margin-bottom: 1rem; box-shadow: 0 2px 8px rgba(0,0,0,0.1); border-left: 4px solid #f59e0b;">
                    <h3 style="margin: 0 0 0.5rem 0; color: #1f2937;">${scheme.name}</h3>
                    <p style="color: #6b7280; font-size: 0.9rem; margin-bottom: 1rem;">${scheme.description}</p>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1rem;">
                        <div>
                            <span style="color: #6b7280; font-size: 0.8rem;">Eligibility</span>
                            <p style="margin: 0.25rem 0; font-size: 0.9rem;">${scheme.eligibility}</p>
                        </div>
                        <div>
                            <span style="color: #6b7280; font-size: 0.8rem;">Amount</span>
                            <p style="margin: 0.25rem 0; font-size: 0.9rem; font-weight: bold;">${scheme.amount}</p>
                        </div>
                    </div>
                    <div style="text-align: right;">
                        <button style="background: #f59e0b; color: white; padding: 0.25rem 0.75rem; border: none; border-radius: 4px; font-size: 0.8rem; cursor: pointer;">
                            Apply Now
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function handleMarketSearch() {
            const query = document.getElementById('voiceInput').value.toLowerCase();
            
            if (query.includes('price') || query.includes('market')) {
                showMarketSection('prices');
            } else if (query.includes('labor') || query.includes('worker')) {
                showMarketSection('laborers');
            } else if (query.includes('equipment') || query.includes('tractor')) {
                showMarketSection('equipment');
            } else if (query.includes('shop') || query.includes('seed')) {
                showMarketSection('shops');
            } else if (query.includes('scheme') || query.includes('government')) {
                showMarketSection('schemes');
            }
        }

        // Initialize disease detection
        document.addEventListener('DOMContentLoaded', function() {
            const uploadArea = document.getElementById('uploadArea');
            const fileInput = document.getElementById('fileInput');
            const imagePreview = document.getElementById('imagePreview');
            const analyzeBtn = document.getElementById('analyzeBtn');

            if (uploadArea && fileInput) {
                uploadArea.addEventListener('click', () => fileInput.click());
                
                fileInput.addEventListener('change', (e) => {
                    if (e.target.files.length) {
                        const file = e.target.files[0];
                        const reader = new FileReader();
                        reader.onload = (e) => {
                            imagePreview.src = e.target.result;
                            imagePreview.style.display = 'block';
                            analyzeBtn.disabled = false;
                        };
                        reader.readAsDataURL(file);
                    }
                });
            }

            // Initialize with home section and sensor data
            showSection('home');
            updateSensorData();
            setInterval(updateSensorData, 30000); // Update every 30 seconds
        });
    </script>
</body>
</html>
