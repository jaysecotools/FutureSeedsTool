// ==================== CONFIGURATION ====================
    const STORAGE_WARN_MB = 4;             // Warn when used >4MB
    const STORAGE_LIMIT_MB = 5;            // Approximate localStorage limit

    // Month display names
    const monthDisplayNames = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];

    // Local storage keys
    const STORAGE_KEY = 'futureSeedsRecords';
    const OBSERVER_KEY = 'futureSeedsObserver';

    // Load records from localStorage
    let savedRecords = JSON.parse(localStorage.getItem(STORAGE_KEY)) || [];

    // Load saved observer name
    let savedObserver = localStorage.getItem(OBSERVER_KEY) || '';

    // Full species list with all species (80+ species)
    const fullSpeciesList = [
        { value: 'Acacia dealbata', display: '<i>Acacia dealbata</i> (Silver Wattle)' },
        { value: 'Acacia genistifolia', display: '<i>Acacia genistifolia</i>' },
        { value: 'Acacia mearnsii', display: '<i>Acacia mearnsii</i> (Black Wattle)' },
        { value: 'Acacia melanoxylon', display: '<i>Acacia melanoxylon</i> (Blackwood)' },
        { value: 'Acacia mucronata', display: '<i>Acacia mucronata</i>' },
        { value: 'Acacia riceana', display: '<i>Acacia riceana</i>' },
        { value: 'Acacia stricta', display: '<i>Acacia stricta</i>' },
        { value: 'Acacia verticillata', display: '<i>Acacia verticillata</i> (Prickly Moses)' },
        { value: 'Acacia terminalis', display: '<i>Acacia terminalis</i>' },
        { value: 'Allocasuarina crassa', display: '<i>Allocasuarina crassa</i> (Rare)' },
        { value: 'Allocasuarina littoralis', display: '<i>Allocasuarina littoralis</i>' },
        { value: 'Allocasuarina monilifera', display: '<i>Allocasuarina monilifera</i>' },
        { value: 'Allocasuarina verticillata', display: '<i>Allocasuarina verticillata</i>' },
        { value: 'Argentipalium dealbatum', display: '<i>Argentipalium dealbatum</i>' },
        { value: 'Banksia marginata', display: '<i>Banksia marginata</i> (Silver Banksia)' },
        { value: 'Bedfordia salicina', display: '<i>Bedfordia salicina</i>' },
        { value: 'Beyeria viscosa', display: '<i>Beyeria viscosa</i>' },
        { value: 'Bursaria spinosa', display: '<i>Bursaria spinosa</i>' },
        { value: 'Melaleuca pallidus', display: '<i>Melaleuca pallidus</i>' },
        { value: 'Juncus pallidus', display: '<i>Juncus pallidus</i>' },
        { value: 'Carex appressa', display: '<i>Carex appressa</i>' },
        { value: 'Carex fascicularis', display: '<i>Carex fascicularis</i> (Semi common)' },
        { value: 'Cassinia aculeata', display: '<i>Cassinia aculeata</i>' },
        { value: 'Chrysocephalum apiculatum', display: '<i>Chrysocephalum apiculatum</i>' },
        { value: 'Coprosma quadrifida', display: '<i>Coprosma quadrifida</i>' },
        { value: 'Correa reflexa', display: '<i>Correa reflexa</i>' },
        { value: 'Craspedia glauca', display: '<i>Craspedia glauca</i>' },
        { value: 'Daviesia latifolia', display: '<i>Daviesia latifolia</i>' },
        { value: 'Dianella tasmanica', display: '<i>Dianella tasmanica</i>' },
        { value: 'Dodonaea filiformis', display: '<i>Dodonaea filiformis</i> (Semi Common)' },
        { value: 'Dodonaea viscosa', display: '<i>Dodonaea viscosa</i>' },
        { value: 'Eucalyptus amygdalina', display: '<i>Eucalyptus amygdalina</i>' },
        { value: 'Eucalyptus coccifera', display: '<i>Eucalyptus coccifera</i> (Semi Common)' },
        { value: 'Eucalyptus tasmaniensis', display: '<i>Eucalyptus tasmaniensis</i>' },
        { value: 'Eucalyptus perinniana', display: '<i>Eucalyptus perinniana</i>' },
        { value: 'Eucalyptus radiata', display: '<i>Eucalyptus radiata</i>' },
        { value: 'Eucalyptus cordata', display: '<i>Eucalyptus cordata</i>' },
        { value: 'Eucalyptus urnigera', display: '<i>Eucalyptus urnigera</i>' },
        { value: 'Eucalyptus vernicosa', display: '<i>Eucalyptus vernicosa</i>' },
        { value: 'Eucalyptus archeri', display: '<i>Eucalyptus archeri</i>' },
        { value: 'Eucalyptus johnstonii', display: '<i>Eucalyptus johnstonii</i>' },
        { value: 'Eucalyptus barberi', display: '<i>Eucalyptus barberi</i>' },
        { value: 'Eucalyptus globulus', display: '<i>Eucalyptus globulus</i>' },
        { value: 'Eucalyptus nitida', display: '<i>Eucalyptus nitida</i> (Common)' },
        { value: 'Eucalyptus obliqua', display: '<i>Eucalyptus obliqua</i>' },
        { value: 'Eucalyptus ovata', display: '<i>Eucalyptus ovata</i>' },
        { value: 'Eucalyptus pauciflora', display: '<i>Eucalyptus pauciflora</i>' },
        { value: 'Eucalyptus pulchella', display: '<i>Eucalyptus pulchella</i>' },
        { value: 'Eucalyptus regnans', display: '<i>Eucalyptus regnans</i>' },
        { value: 'Eucalyptus tenuiramis', display: '<i>Eucalyptus tenuiramis</i>' },
        { value: 'Eucalyptus viminalis', display: '<i>Eucalyptus viminalis</i>' },
        { value: 'Eucryphia lucida', display: '<i>Eucryphia lucida</i>' },
        { value: 'Ficinia nodosa', display: '<i>Ficinia nodosa</i>' },
        { value: 'Grevillea australis', display: '<i>Grevillea australis</i>' },
        { value: 'Hakea epiglottis', display: '<i>Hakea epiglottis</i>' },
        { value: 'Hakea lissosperma', display: '<i>Hakea lissosperma</i>' },
        { value: 'Hakea macrocarpa', display: '<i>Hakea macrocarpa</i>' },
        { value: 'Hakea nodosa', display: '<i>Hakea nodosa</i>' },
        { value: 'Hakea sericea', display: '<i>Hakea sericea</i>' },
        { value: 'Lasiopetalum macrophyllum', display: '<i>Lasiopetalum macrophyllum</i> (Semi Common/Coastal)' },
        { value: 'Leptospermum lanigerum', display: '<i>Leptospermum lanigerum</i>' },
        { value: 'Leptospermum rupestre', display: '<i>Leptospermum rupestre</i>' },
        { value: 'Leptospermum scoparium', display: '<i>Leptospermum scoparium</i> (Manuka)' },
        { value: 'Linum marginale', display: '<i>Linum marginale</i>' },
        { value: 'Lomandra longifolia', display: '<i>Lomandra longifolia</i>' },
        { value: 'Melaleuca ericifolia', display: '<i>Melaleuca ericifolia</i>' },
        { value: 'Melaleuca gibbosa', display: '<i>Melaleuca gibbosa</i> (Semi common)' },
        { value: 'Melaleuca pustulata', display: '<i>Melaleuca pustulata</i>' },
        { value: 'Melaleuca squarrosa', display: '<i>Melaleuca squarrosa</i> (Semi Common)' },
        { value: 'Olearia phlogopappa', display: '<i>Olearia phlogopappa</i>' },
        { value: 'Olearia argophylla', display: '<i>Olearia argophylla</i>' },
        { value: 'Olearia ramulosa', display: '<i>Olearia ramulosa</i>' },
        { value: 'Oxylobium ellipticum', display: '<i>Oxylobium ellipticum</i>' },
        { value: 'Ozothamnus ferrugineus', display: '<i>Ozothamnus ferrugineus</i>' },
        { value: 'Pelargonium australe', display: '<i>Pelargonium australe</i>' },
        { value: 'Pittosporum bicolor', display: '<i>Pittosporum bicolor</i>' },
        { value: 'Poa labillardierei', display: '<i>Poa labillardierei</i>' },
        { value: 'Pomaderris apetala', display: '<i>Pomaderris apetala</i>' },
        { value: 'Pomaderris elliptica', display: '<i>Pomaderris elliptica</i>' },
        { value: 'Pultenaea juniperina', display: '<i>Pultenaea juniperina</i>' },
        { value: 'Pultenaea pedunculata', display: '<i>Pultenaea pedunculata</i> (Semi Common)' },
        { value: 'Stylidium armeria', display: '<i>Stylidium armeria</i> (Common coastal)' },
        { value: 'Tasmannia lanceolata', display: '<i>Tasmannia lanceolata</i>' },
        { value: 'Themeda triandra', display: '<i>Themeda triandra</i>' },
        { value: 'Telopea truncata', display: '<i>Telopea truncata</i>' },
        { value: 'Westringia brevifolia', display: '<i>Westringia brevifolia</i>' },
        { value: 'Exocarpos cupressiformis', display: '<i>Exocarpos cupressiformis</i>' },
        { value: 'Gahnia radula', display: '<i>Gahnia radula</i>' },
        { value: 'Styphelia humifusa', display: '<i>Styphelia humifusa</i>' },
        { value: 'Pimelea humilis', display: '<i>Pimelea humilis</i>' }
    ];

    // Region presets
    const regionPresets = {
        northWest: { lat: -41.05, lon: 145.90, name: "North West (Burnie/Devonport)" },
        north: { lat: -41.43, lon: 147.14, name: "North (Launceston)" },
        south: { lat: -42.88, lon: 147.33, name: "South (Hobart)" },
        westCoast: { lat: -42.15, lon: 145.32, name: "West Coast (Strahan/Queenstown)" },
        eastCoast: { lat: -41.73, lon: 148.25, name: "East Coast (St Helens/Bicheno)" }
    };

    // Track location mode
    let usingMapMode = false;

    // Weather loading state
    let isLoadingWeather = false;
    let weatherLoadTimeout = null;
    
    // Store the last loaded weather data
    let lastWeatherData = null;

    // Rate limiting for reverse geocoding
    let lastGeocodeTime = 0;

    // Templates (removed photo references)
    const templates = {
        postFire: {
            fireHistory: 'recent',
            notes: 'Post-fire regeneration monitoring',
            seedMaturity: 'early',
        },
        peakFlower: {
            fullFlower: true,
            seedMaturity: 'early',
            notes: 'Peak flowering observed',
        },
        seedCollection: {
            seedPod: true,
            seedMaturity: 'mature',
            notes: 'Seed collection site',
        },
        pollinatorSurvey: {
            notes: 'Pollinator survey location',
        }
    };

    // Initialize map
    let map;
    let marker;

    // Track selected records for export
    let selectedRecordIds = new Set();

// ========== ENHANCED SPECIES SELECTOR ==========
let currentSpeciesList = [...fullSpeciesList];
let selectedSpeciesIndex = 0;
let filteredSpeciesList = [];

function initializeEnhancedSpeciesSelector() {
    const speciesSelect = document.getElementById('speciesSelect');
    const speciesDropdown = document.getElementById('speciesDropdown');
    const speciesSelectButton = document.getElementById('speciesSelectButton');
    const speciesSearchInput = document.getElementById('speciesSearchInput');
    const speciesOptions = document.getElementById('speciesOptions');
    const selectedSpeciesDisplay = document.getElementById('selectedSpeciesDisplay');
    
    // Populate the hidden select (for form submission)
    populateHiddenSelect();
    
    // Set initial selected value (Acacia verticillata)
    const initialValue = 'Acacia verticillata';
    
    // Find the display text for the initial value
    const initialSpecies = fullSpeciesList.find(s => s.value === initialValue);
    if (initialSpecies) {
        // Strip HTML tags for display
        const tempDiv = document.createElement('div');
        tempDiv.innerHTML = initialSpecies.display;
        selectedSpeciesDisplay.textContent = tempDiv.textContent || tempDiv.innerText || initialSpecies.display;
    }
    
    // Toggle dropdown on button click
    speciesSelectButton.addEventListener('click', function(e) {
        e.stopPropagation();
        if (!speciesDropdown.classList.contains('show')) {
            showSpeciesDropdown();
        } else {
            speciesDropdown.classList.remove('show');
        }
    });
    
    // Search functionality
    speciesSearchInput.addEventListener('input', function() {
        filterSpecies(this.value);
    });
    
    // Keyboard navigation
    speciesSearchInput.addEventListener('keydown', function(e) {
        handleSpeciesKeyboard(e);
    });
    
    // Close dropdown when clicking outside
    document.addEventListener('click', function(e) {
        if (!e.target.closest('.species-select-container')) {
            speciesDropdown.classList.remove('show');
        }
    });
    
    // Initialize with all species
    filterSpecies('');
    
    // Set initial selected value
    updateSelectedSpecies(initialValue);
}

function populateHiddenSelect() {
    const select = document.getElementById('speciesSelect');
    select.innerHTML = '';
    currentSpeciesList.forEach(species => {
        const option = document.createElement('option');
        option.value = species.value;
        option.innerHTML = species.display;
        select.appendChild(option);
    });
}

function showSpeciesDropdown() {
    const dropdown = document.getElementById('speciesDropdown');
    dropdown.classList.add('show');
    document.getElementById('speciesSearchInput').focus();
    document.getElementById('speciesSearchInput').select();
}

function filterSpecies(searchTerm) {
    const searchLower = searchTerm.toLowerCase();
    filteredSpeciesList = currentSpeciesList.filter(species => 
        species.value.toLowerCase().includes(searchLower) || 
        species.display.toLowerCase().includes(searchLower)
    );
    renderSpeciesOptions();
}

function renderSpeciesOptions() {
    const container = document.getElementById('speciesOptions');
    const currentValue = document.getElementById('speciesSelect').value;
    
    if (filteredSpeciesList.length === 0) {
        container.innerHTML = '<div class="no-results">No matching species found</div>';
        return;
    }
    
    // Reset selected index if out of bounds
    if (selectedSpeciesIndex >= filteredSpeciesList.length) {
        selectedSpeciesIndex = 0;
    }
    
    container.innerHTML = filteredSpeciesList.map((species, index) => {
        const isSelected = species.value === currentValue;
        const isHighlighted = index === selectedSpeciesIndex;
        const classes = ['species-option'];
        if (isSelected) classes.push('selected');
        if (isHighlighted) classes.push('highlighted');
        
        return `<div class="${classes.join(' ')}" data-value="${species.value}" data-index="${index}">${species.display}</div>`;
    }).join('');
    
    // Add click handlers to options
    document.querySelectorAll('.species-option').forEach(option => {
        option.addEventListener('click', function(e) {
            e.stopPropagation();
            const value = this.dataset.value;
            updateSelectedSpecies(value);
            document.getElementById('speciesDropdown').classList.remove('show');
        });
    });
}

function updateSelectedSpecies(value) {
    const select = document.getElementById('speciesSelect');
    const selectedSpeciesDisplay = document.getElementById('selectedSpeciesDisplay');
    
    // Update hidden select
    select.value = value;
    
    // Update display text
    const species = fullSpeciesList.find(s => s.value === value);
    if (species) {
        // Strip HTML tags for display in the button
        const tempDiv = document.createElement('div');
        tempDiv.innerHTML = species.display;
        selectedSpeciesDisplay.textContent = tempDiv.textContent || tempDiv.innerText || species.display;
    }
    
    // Trigger change event
    const event = new Event('change', { bubbles: true });
    select.dispatchEvent(event);
    
    // Update display
    updateSpeciesInfo();
}

function handleSpeciesKeyboard(e) {
    const options = document.querySelectorAll('.species-option:not(.no-results)');
    
    switch(e.key) {
        case 'ArrowDown':
            e.preventDefault();
            if (options.length > 0) {
                selectedSpeciesIndex = Math.min(selectedSpeciesIndex + 1, options.length - 1);
                highlightOption(selectedSpeciesIndex);
            }
            break;
            
        case 'ArrowUp':
            e.preventDefault();
            if (options.length > 0) {
                selectedSpeciesIndex = Math.max(selectedSpeciesIndex - 1, 0);
                highlightOption(selectedSpeciesIndex);
            }
            break;
            
        case 'Enter':
            e.preventDefault();
            if (options.length > 0 && options[selectedSpeciesIndex]) {
                const value = options[selectedSpeciesIndex].dataset.value;
                updateSelectedSpecies(value);
                document.getElementById('speciesDropdown').classList.remove('show');
            }
            break;
            
        case 'Escape':
            document.getElementById('speciesDropdown').classList.remove('show');
            break;
    }
}

function highlightOption(index) {
    // Remove highlight from all
    document.querySelectorAll('.species-option').forEach(opt => {
        opt.classList.remove('highlighted');
    });
    
    // Add highlight to current
    const option = document.querySelector(`.species-option[data-index="${index}"]`);
    if (option) {
        option.classList.add('highlighted');
        option.scrollIntoView({ block: 'nearest', behavior: 'smooth' });
    }
}

// ===== UPDATE NOTIFICATION =====
const APP_VERSION = '4.0'; // Major update with requested changes
const SEEN_VERSION_KEY = 'futureSeedsSeenVersion';

function showUpdatePopup() {
    const popup = document.createElement('div');
    popup.id = 'updatePopup';
    popup.style.cssText = `
        position: fixed; top: 20px; left: 50%; transform: translateX(-50%);
        background: #f6f9ed; border: 4px solid #dbb15a; border-radius: 36px;
        padding: 2rem; box-shadow: 0 25px 50px -12px #0b2f1a; z-index: 10000;
        max-width: 450px; text-align: center;
    `;
    popup.innerHTML = `
        <h2 style="color:#1f5c33;">✨ What's New in v${APP_VERSION}</h2>
        <ul style="text-align:left; margin:1rem 0;">
            <li>✅ All priority species added</li>
            <li>✅ Searchable species selector</li>
            <li>✅ Smart search option to type into search</li>
            <li>✅ Dynamic month display (auto-updates)</li>
            <li>✅ Check boxes to select records</li>
        </ul>
        <button id="closeUpdatePopup" class="btn btn-primary" style="font-size:1.2rem;">Got it!</button>
    `;
    document.body.appendChild(popup);
    
    document.getElementById('closeUpdatePopup').addEventListener('click', () => {
        popup.remove();
        localStorage.setItem(SEEN_VERSION_KEY, APP_VERSION);
    });
}

// On page load
window.addEventListener('load', function() {
    const seenVersion = localStorage.getItem(SEEN_VERSION_KEY);
    if (seenVersion !== APP_VERSION) {
        setTimeout(showUpdatePopup, 500);
    }
});

    // ========== STORAGE METER ==========
    function updateStorageMeter() {
        try {
            const data = localStorage.getItem(STORAGE_KEY);
            const totalSize = data ? new Blob([data]).size : 0;
            const totalSizeMB = (totalSize / (1024 * 1024)).toFixed(2);
            document.getElementById('storageMeter').innerText = `${totalSizeMB} MB used`;
            
            const warningEl = document.getElementById('storageWarning');
            if (totalSizeMB > STORAGE_WARN_MB) {
                warningEl.style.display = 'block';
                warningEl.innerHTML = `⚠️ Storage: ${totalSizeMB}MB used (near ${STORAGE_LIMIT_MB}MB limit). Export and clear some records if you have issues saving.`;
            } else {
                warningEl.style.display = 'none';
            }
            return parseFloat(totalSizeMB);
        } catch (e) {
            return 0;
        }
    }

    // ========== EMAIL CSV FUNCTIONALITY ==========
    function emailDataAsCSV() {
        if (savedRecords.length === 0) { 
            alert('No records to email'); 
            return; 
        }
        
        const csvString = generateCSVString(savedRecords);
        const blob = new Blob([csvString], { type: 'text/csv' });
        const url = URL.createObjectURL(blob);
        
        // Create mailto link with subject and body
        const subject = encodeURIComponent('Future Seeds Program Data Export');
        const body = encodeURIComponent(
            `Future Seeds Program Data\n` +
            `Total Records: ${savedRecords.length}\n` +
            `Export Date: ${new Date().toLocaleDateString()}\n\n` +
            `CSV data is attached. Please download the file from the link below:\n\n` +
            `${url}\n\n` +
            `Or save the attached file manually.`
        );
        
        // For email, we need to provide a download link since we can't directly attach
        // On mobile, this will open email app with instructions
        window.location.href = `mailto:?subject=${subject}&body=${body}`;
        
        setTimeout(() => URL.revokeObjectURL(url), 10000);
        document.getElementById('outputBox').innerText = `📧 Email client opened with CSV download link`;
    }

    // ========== WEATHER ==========
    function getWeatherDescription(code) {
        const weatherCodes = {
            0: 'Clear sky',
            1: 'Mainly clear',
            2: 'Partly cloudy',
            3: 'Overcast',
            45: 'Fog',
            48: 'Rime fog',
            51: 'Light drizzle',
            53: 'Moderate drizzle',
            55: 'Dense drizzle',
            56: 'Freezing drizzle',
            57: 'Dense freezing drizzle',
            61: 'Slight rain',
            63: 'Moderate rain',
            65: 'Heavy rain',
            66: 'Freezing rain',
            67: 'Heavy freezing rain',
            71: 'Slight snow',
            73: 'Moderate snow',
            75: 'Heavy snow',
            77: 'Snow grains',
            80: 'Slight rain showers',
            81: 'Moderate rain showers',
            82: 'Violent rain showers',
            85: 'Slight snow showers',
            86: 'Heavy snow showers',
            95: 'Thunderstorm',
            96: 'Thunderstorm with hail',
            99: 'Heavy thunderstorm with hail'
        };
        return weatherCodes[code] || 'Unknown conditions';
    }

    async function loadCurrentWeather(showFeedback = true) {
        if (weatherLoadTimeout) clearTimeout(weatherLoadTimeout);
        if (isLoadingWeather) return;
        
        const lat = document.getElementById('lat').value;
        const lon = document.getElementById('lon').value;
        const autoBtn = document.getElementById('autoWeatherBtn');
        const originalText = '<span>🌤️</span> Auto-load Current Weather';
        
        try {
            isLoadingWeather = true;
            if (showFeedback && autoBtn) {
                autoBtn.innerHTML = '<span>⏳</span> Loading weather...';
                autoBtn.disabled = true;
            }
            document.getElementById('outputBox').innerText = '🌤️ Loading weather data from Open-Meteo...';
            
            const response = await fetch(
                `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current=temperature_2m,relative_humidity_2m,weather_code,wind_speed_10m,pressure_msl&daily=temperature_2m_min,temperature_2m_max,precipitation_sum&timezone=auto`
            );
            
            if (!response.ok) throw new Error('Weather service temporarily unavailable');
            
            const data = await response.json();
            
            if (data.current && data.daily) {
                lastWeatherData = {
                    latitude: parseFloat(lat),
                    longitude: parseFloat(lon),
                    current: {
                        temperature: data.current.temperature_2m,
                        humidity: data.current.relative_humidity_2m,
                        weatherCode: data.current.weather_code,
                        weatherDescription: getWeatherDescription(data.current.weather_code),
                        windSpeed: data.current.wind_speed_10m,
                        pressure: data.current.pressure_msl,
                        timestamp: new Date().toISOString()
                    },
                    daily: {
                        minTemp: data.daily.temperature_2m_min[0],
                        maxTemp: data.daily.temperature_2m_max[0],
                        precipitation: data.daily.precipitation_sum[0],
                        date: data.daily.time[0]
                    },
                    timezone: data.timezone
                };
                
                const minTemp = lastWeatherData.daily.minTemp;
                const maxTemp = lastWeatherData.daily.maxTemp;
                
                document.getElementById('actualMinTemp').value = minTemp.toFixed(1);
                document.getElementById('actualMaxTemp').value = maxTemp.toFixed(1);
                document.getElementById('bomStation').value = `Open-Meteo - ${lastWeatherData.current.weatherDescription} (${lastWeatherData.current.temperature}°C, ${lastWeatherData.current.humidity}% RH)`;
                
                updateTempDisplay();
                
                document.getElementById('outputBox').innerText = 
                    `✅ Weather loaded successfully!\n` +
                    `📍 Location: ${lat}, ${lon}\n` +
                    `🌡️ Current: ${lastWeatherData.current.temperature}°C\n` +
                    `💧 Humidity: ${lastWeatherData.current.humidity}%\n` +
                    `💨 Wind: ${lastWeatherData.current.windSpeed} km/h\n` +
                    `📊 Today's range: ${minTemp.toFixed(1)}°C - ${maxTemp.toFixed(1)}°C\n` +
                    `☁️ Conditions: ${lastWeatherData.current.weatherDescription}\n` +
                    `🌧️ Precipitation: ${lastWeatherData.daily.precipitation} mm\n` +
                    `⚡ Data from Open-Meteo (free, no API key)`;
                
                if (showFeedback && autoBtn) {
                    autoBtn.innerHTML = '<span>✅</span> Loaded! ✓';
                    weatherLoadTimeout = setTimeout(() => {
                        if (autoBtn) {
                            autoBtn.innerHTML = originalText;
                            autoBtn.disabled = false;
                        }
                        weatherLoadTimeout = null;
                    }, 2000);
                } else if (autoBtn) {
                    autoBtn.disabled = false;
                }
            } else {
                throw new Error('Invalid weather data received');
            }
        } catch (error) {
            console.error('Weather fetch failed:', error);
            document.getElementById('outputBox').innerText = '❌ Failed to load weather data. Please try again or enter manually.';
            if (showFeedback && autoBtn) {
                autoBtn.innerHTML = '<span>❌</span> Failed - Try Again';
                weatherLoadTimeout = setTimeout(() => {
                    if (autoBtn) {
                        autoBtn.innerHTML = originalText;
                        autoBtn.disabled = false;
                    }
                    weatherLoadTimeout = null;
                }, 2000);
            } else if (autoBtn) {
                autoBtn.disabled = false;
            }
        } finally {
            isLoadingWeather = false;
        }
    }

    // ========== PHOTO HANDLING (REMOVED - just placeholder functions) ==========
    // These functions are kept as empty to prevent errors, but photo UI is hidden via CSS
    function clearAllPhotos() {}
    function openCamera() {}
    function handleNewPhotos(files) {}
    function updatePhotoPreviews() {}
    function removePhoto(index) {}
    function compressPhotos(files) {}
    function compressSinglePhoto(file) { return Promise.resolve(file); }

    // ========== OTHER FUNCTIONS ==========

    function toggleGuide() {
        document.getElementById('guidePanel').classList.toggle('show');
    }

    function toggleMap(show) {
        const mapEl = document.getElementById('map');
        const showBtn = document.getElementById('showMapBtn');
        const hideBtn = document.getElementById('hideMapBtn');
        if (show) {
            mapEl.classList.add('show');
            showBtn.classList.add('active');
            hideBtn.classList.remove('active');
            setTimeout(() => { if (map) map.invalidateSize(); }, 100);
        } else {
            mapEl.classList.remove('show');
            showBtn.classList.remove('active');
            hideBtn.classList.add('active');
        }
    }

    function toggleLocationMode() {
        if (usingMapMode) {
            enableQuickRegionMode();
            updateFromRegion();
            document.getElementById('toggleLocationMode').innerHTML = '🔄 Switch to Map Mode';
        } else {
            enableMapMode();
            document.getElementById('toggleLocationMode').innerHTML = '🔄 Switch to Quick Region';
        }
    }

    function enableMapMode() {
        usingMapMode = true;
        document.getElementById('locationMode').innerText = '📍 Map Mode';
        document.getElementById('locationMode').style.background = '#d16b4b';
        document.getElementById('mapModeIndicator').innerText = '✅ Map active';
        document.getElementById('mapModeIndicator').style.background = '#d16b4b';
        document.getElementById('regionSelect').classList.add('map-active');
        document.getElementById('regionSelect').disabled = true;
        document.getElementById('mapInUseBadge').classList.add('show');
        document.getElementById('locationNote').innerHTML = '📍 Using precise map coordinates. Region dropdown shows "📍 Map in use".';
        document.getElementById('toggleLocationMode').innerHTML = '🔄 Switch to Quick Region';
    }

    function enableQuickRegionMode() {
        usingMapMode = false;
        document.getElementById('locationMode').innerText = '⚡ Quick Region';
        document.getElementById('locationMode').style.background = '#4a90e2';
        document.getElementById('mapModeIndicator').innerText = 'Click map to activate';
        document.getElementById('mapModeIndicator').style.background = '#4a90e2';
        document.getElementById('regionSelect').classList.remove('map-active');
        document.getElementById('regionSelect').disabled = false;
        document.getElementById('mapInUseBadge').classList.remove('show');
        document.getElementById('locationNote').innerHTML = '⚡ Using Quick Region mode. Click map or use "My Location" for precise coordinates.';
        document.getElementById('toggleLocationMode').innerHTML = '🔄 Switch to Map Mode';
    }

    function getUserLocation() {
        if (!navigator.geolocation) {
            alert('Geolocation is not supported by your browser');
            return;
        }
        document.getElementById('outputBox').innerText = '📍 Getting your location...';
        navigator.geolocation.getCurrentPosition(
            (position) => {
                const lat = position.coords.latitude;
                const lng = position.coords.longitude;
                if (marker) {
                    marker.setLatLng([lat, lng]);
                    map.setView([lat, lng], 12);
                }
                updateCoordinates(lat, lng, true);
                reverseGeocode(lat, lng);
                enableMapMode();
                document.getElementById('outputBox').innerText = `📍 Location captured: ${lat.toFixed(4)}, ${lng.toFixed(4)}`;
                setTimeout(() => loadCurrentWeather(false), 500);
            },
            (error) => {
                let errorMessage = 'Location error: ';
                switch(error.code) {
                    case error.PERMISSION_DENIED: errorMessage += 'Please allow location access'; break;
                    case error.POSITION_UNAVAILABLE: errorMessage += 'Location information unavailable'; break;
                    case error.TIMEOUT: errorMessage += 'Location request timed out'; break;
                    default: errorMessage += 'Unknown error';
                }
                alert(errorMessage);
                document.getElementById('outputBox').innerText = '❌ ' + errorMessage;
            },
            { enableHighAccuracy: true, timeout: 10000, maximumAge: 0 }
        );
    }

    function reverseGeocode(lat, lng) {
        const now = Date.now();
        if (now - lastGeocodeTime < 1000) {
            setTimeout(() => reverseGeocode(lat, lng), 1000);
            return;
        }
        lastGeocodeTime = now;
        fetch(`https://nominatim.openstreetmap.org/reverse?format=json&lat=${lat}&lon=${lng}&zoom=18&addressdetails=1`)
            .then(response => response.json())
            .then(data => {
                if (data.display_name) {
                    const locationParts = [];
                    if (data.address.suburb) locationParts.push(data.address.suburb);
                    if (data.address.town) locationParts.push(data.address.town);
                    if (data.address.city) locationParts.push(data.address.city);
                    if (data.address.state) locationParts.push(data.address.state);
                    if (locationParts.length > 0) {
                        document.getElementById('siteName').value = locationParts.join(', ');
                    }
                }
            })
            .catch(error => console.log('Reverse geocoding failed:', error));
    }

function initMap() {
    // Make sure the map container exists and is visible
    const mapContainer = document.getElementById('map');
    if (!mapContainer) {
        console.error('Map container not found');
        return;
    }
    
    // Ensure the map container has dimensions
    mapContainer.style.height = '300px';
    mapContainer.style.width = '100%';
    mapContainer.style.display = 'block';
    
    // Initialize map with default view (Tasmania)
    map = L.map('map', {
        center: [-42.88, 147.33],
        zoom: 7,
        zoomControl: true
    });
    
    // Add tile layer (OpenStreetMap)
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '© OpenStreetMap contributors',
        maxZoom: 19
    }).addTo(map);
    
    // Add draggable marker
    marker = L.marker([-42.88, 147.33], { 
        draggable: true,
        autoPan: true
    }).addTo(map);
    
    // Marker drag event
    marker.on('dragend', function(e) {
        const latlng = marker.getLatLng();
        updateCoordinates(latlng.lat, latlng.lng, true);
        enableMapMode();
    });
    
    // Map click event
    map.on('click', function(e) {
        marker.setLatLng(e.latlng);
        updateCoordinates(e.latlng.lat, e.latlng.lng, true);
        enableMapMode();
    });
    
    // Force map to update its size (important after initialization)
    setTimeout(() => {
        if (map) {
            map.invalidateSize();
        }
    }, 200);
    
    console.log('Map initialized successfully');
}

    function updateCoordinates(lat, lng, fromMap = false) {
        document.getElementById('lat').value = lat.toFixed(4);
        document.getElementById('lon').value = lng.toFixed(4);
        if (fromMap) {
            document.getElementById('coordSource').value = 'Map selection';
            setTimeout(() => loadCurrentWeather(false), 500);
        } else {
            const region = document.getElementById('regionSelect').value;
            document.getElementById('coordSource').value = `Quick Region (${regionPresets[region].name})`;
            setTimeout(() => loadCurrentWeather(false), 500);
        }
    }

    function updateFromRegion() {
        if (usingMapMode) return;
        const region = document.getElementById('regionSelect').value;
        const preset = regionPresets[region];
        document.getElementById('lat').value = preset.lat.toFixed(4);
        document.getElementById('lon').value = preset.lon.toFixed(4);
        document.getElementById('coordSource').value = `Quick Region (${preset.name})`;
        if (marker) {
            marker.setLatLng([preset.lat, preset.lon]);
            map.setView([preset.lat, preset.lon], 8);
        }
    }

    function getCurrentMonthIndex() {
        const dateStr = document.getElementById('obsDate').value;
        if (dateStr) {
            const d = new Date(dateStr + 'T12:00:00');
            return d.getMonth();
        }
        return new Date().getMonth();
    }

    function updateMonthDisplay() {
        const monthIndex = getCurrentMonthIndex();
        const year = new Date().getFullYear();
        document.getElementById('currentMonthDisplay').innerHTML = `📆 ${monthDisplayNames[monthIndex]} ${year} · weather data ready`;
    }

    function updateTempDisplay() {
        const minTemp = document.getElementById('actualMinTemp').value;
        const maxTemp = document.getElementById('actualMaxTemp').value;
        document.getElementById('displayMin').innerText = minTemp ? minTemp + '°C' : '--°C';
        document.getElementById('displayMax').innerText = maxTemp ? maxTemp + '°C' : '--°C';
    }

    function updateSpeciesInfo() {
        const select = document.getElementById('speciesSelect');
        const species = select.value;
        let displayName = species;
        const speciesObj = fullSpeciesList.find(s => s.value === species);
        if (speciesObj) {
            displayName = speciesObj.display;
        } else {
            displayName = `🌱 <i>${species}</i> (Custom)`;
        }
        document.getElementById('speciesDisplay').innerHTML = displayName;
    }

    function handleFloweringNone() {
        const floweringNone = document.getElementById('floweringNone');
        if (floweringNone.checked) {
            document.getElementById('bud').checked = false;
            document.getElementById('earlyFlower').checked = false;
            document.getElementById('fullFlower').checked = false;
            document.getElementById('petalFall').checked = false;
            document.getElementById('seedPod').checked = false;
        }
    }

    function handlePollinatorsNone() {
        const pollinatorsNone = document.getElementById('pollinatorsNone');
        if (pollinatorsNone.checked) {
            document.getElementById('honeybee').checked = false;
            document.getElementById('nativeBee').checked = false;
            document.getElementById('fly').checked = false;
            document.getElementById('beetle').checked = false;
            document.getElementById('wasp').checked = false;
            document.getElementById('butterfly').checked = false;
            document.getElementById('birds').checked = false;
            document.getElementById('otherPollinators').value = '';
        }
    }

    function applyTemplate(templateName) {
        const template = templates[templateName];
        if (templateName === 'postFire') {
            document.getElementById('fullFlower').checked = false;
            document.getElementById('seedPod').checked = false;
        } else if (templateName === 'peakFlower') {
            document.getElementById('fireHistory').value = '';
        } else if (templateName === 'seedCollection') {
            document.getElementById('fireHistory').value = '';
        } else if (templateName === 'pollinatorSurvey') {
            document.getElementById('fireHistory').value = '';
            document.getElementById('seedMaturity').value = '';
        }
        if (template.fireHistory) document.getElementById('fireHistory').value = template.fireHistory;
        if (template.notes) document.getElementById('notes').value = template.notes;
        if (template.seedMaturity) document.getElementById('seedMaturity').value = template.seedMaturity;
        if (template.fullFlower) document.getElementById('fullFlower').checked = true;
        if (template.seedPod) document.getElementById('seedPod').checked = true;
        document.getElementById('outputBox').innerText = `✅ Applied template: ${templateName}`;
    }

    function validateRequired() {
        const errors = [];
        const observer = document.getElementById('observer').value.trim();
        if (!observer) errors.push('Observer name is required');
        const date = document.getElementById('obsDate').value;
        if (!date) errors.push('Date is required');
        const floweringSelected = ['bud', 'earlyFlower', 'fullFlower', 'petalFall', 'seedPod'].some(id => document.getElementById(id).checked);
        const floweringNone = document.getElementById('floweringNone').checked;
        if (!floweringSelected && !floweringNone) errors.push('Either select a flowering stage or check "None"');
        
        const pollinatorsSelected = ['honeybee', 'nativeBee', 'fly', 'beetle', 'wasp', 'butterfly', 'birds'].some(id => document.getElementById(id).checked);
        const pollinatorsNone = document.getElementById('pollinatorsNone').checked;
        const otherPollinators = document.getElementById('otherPollinators').value.trim();
        if (!pollinatorsSelected && !otherPollinators && !pollinatorsNone) errors.push('Either select pollinators, describe others, or check "None"');
        return errors;
    }

    function showErrors(errors) {
        const panel = document.getElementById('warningsPanel');
        if (errors.length > 0) {
            panel.style.display = 'block';
            panel.innerHTML = '❌ Required Fields Missing:<br>' + errors.join('<br>');
            return false;
        } else {
            panel.style.display = 'none';
            return true;
        }
    }

    function collectFormData() {
        const region = document.getElementById('regionSelect').value;
        const monthIndex = getCurrentMonthIndex();
        const monthName = monthDisplayNames[monthIndex];
        const observer = document.getElementById('observer').value.trim();
        if (observer) localStorage.setItem(OBSERVER_KEY, observer);

        const getOptionalNumber = (id) => {
            const val = document.getElementById(id).value;
            return val ? parseFloat(val) : null;
        };
        const getOptionalString = (id) => {
            const val = document.getElementById(id).value;
            return val || null;
        };

        const weatherData = {
            month: monthName,
            year: new Date().getFullYear(),
            minTemp: getOptionalNumber('actualMinTemp'),
            maxTemp: getOptionalNumber('actualMaxTemp'),
            station: getOptionalString('bomStation'),
            stationId: getOptionalString('stationId'),
            dataType: lastWeatherData ? "Open-Meteo Auto" : "Manual Entry"
        };

        if (lastWeatherData) {
            weatherData.autoWeather = {
                latitude: lastWeatherData.latitude,
                longitude: lastWeatherData.longitude,
                current: lastWeatherData.current,
                daily: lastWeatherData.daily,
                timezone: lastWeatherData.timezone,
                loadedAt: lastWeatherData.current.timestamp
            };
        }

        return {
            id: Date.now(),
            timestamp: new Date().toISOString(),
            program: "Future Seeds Program",
            locationMode: usingMapMode ? "precise_map" : "quick_region",
            observer: observer,
            collectionDate: document.getElementById('obsDate').value,
            species: document.getElementById('speciesSelect').value,
            location: {
                region: usingMapMode ? "Precise Map Location" : regionPresets[region].name,
                regionCode: usingMapMode ? "map_selected" : region,
                siteName: getOptionalString('siteName'),
                latitude: parseFloat(document.getElementById('lat').value),
                longitude: parseFloat(document.getElementById('lon').value),
                coordinateSource: document.getElementById('coordSource').value,
                locationMode: usingMapMode ? "precise_map" : "quick_region"
            },
            phenology: {
                flowering: {
                    bud: document.getElementById('bud').checked,
                    earlyFlower: document.getElementById('earlyFlower').checked,
                    fullFlower: document.getElementById('fullFlower').checked,
                    petalFall: document.getElementById('petalFall').checked,
                    seedPod: document.getElementById('seedPod').checked,
                    none: document.getElementById('floweringNone').checked
                },
                pollinators: {
                    honeybee: document.getElementById('honeybee').checked,
                    nativeBee: document.getElementById('nativeBee').checked,
                    fly: document.getElementById('fly').checked,
                    beetle: document.getElementById('beetle').checked,
                    wasp: document.getElementById('wasp').checked,
                    butterfly: document.getElementById('butterfly').checked,
                    birds: document.getElementById('birds').checked,
                    other: getOptionalString('otherPollinators'),
                    none: document.getElementById('pollinatorsNone').checked
                },
                seedMaturity: getOptionalString('seedMaturity')
            },
            siteHistory: {
                fire: getOptionalString('fireHistory'),
                notes: getOptionalString('notes')
            },
            weather: weatherData
            // No photos field
        };
    }

    // ========== SAVE RECORD ==========
    async function saveRecord() {
        // Save observer immediately
        const observer = document.getElementById('observer').value.trim();
        if (observer) {
            localStorage.setItem(OBSERVER_KEY, observer);
            savedObserver = observer;
        }
        
        updateTempDisplay();
        const errors = validateRequired();
        if (!showErrors(errors)) return;
        
        const data = collectFormData();
        
        // Estimate size (much smaller without photos)
        const estimatedSize = new Blob([JSON.stringify(data)]).size;
        const estimatedMB = estimatedSize / (1024 * 1024);
        
        // Check current storage usage
        const currentUsageMB = updateStorageMeter();
        const projectedUsage = currentUsageMB + estimatedMB;
        
        if (projectedUsage > STORAGE_LIMIT_MB) {
            if (!confirm(`⚠️ This would push storage to ${projectedUsage.toFixed(2)} MB (near the ${STORAGE_LIMIT_MB} MB limit). Continue anyway?`)) {
                return;
            }
        }
        
        savedRecords.push(data);
        
        try {
            localStorage.setItem(STORAGE_KEY, JSON.stringify(savedRecords));
            displayRecords();
            updateStats();
            updateStorageMeter();
            
            document.getElementById('outputBox').innerText = 
                `✅ Record saved successfully!\n` +
                `Observer: ${data.observer}\n` +
                `Date: ${data.collectionDate}\n` +
                `Species: ${data.species}\n` +
                `Location: ${data.location.region}\n` +
                `Weather: ${data.weather.minTemp || '--'}°C / ${data.weather.maxTemp || '--'}°C\n` +
                `Total records: ${savedRecords.length}`;
            
            resetForm();
            
        } catch (quotaError) {
            console.error('Quota exceeded:', quotaError);
            savedRecords.pop();
            alert('Storage quota exceeded. Please export and delete some old records.');
        }
    }

    // ========== CSV GENERATION ==========
    function generateCSVString(records) {
        if (records.length === 0) return '';
        
        // Define CSV headers
        const headers = [
            'ID', 'Timestamp', 'Program', 'Observer', 'Collection Date', 'Species',
            'Location Mode', 'Region', 'Site Name', 'Latitude', 'Longitude',
            'Flowering - Bud', 'Flowering - Early', 'Flowering - Full', 
            'Flowering - Petal Fall', 'Flowering - Seed Pod', 'Flowering - None',
            'Pollinator - Honeybee', 'Pollinator - Native Bee', 'Pollinator - Fly',
            'Pollinator - Beetle', 'Pollinator - Wasp', 'Pollinator - Butterfly/Moth',
            'Pollinator - Birds', 'Pollinator - Other', 'Pollinator - None',
            'Seed Maturity', 'Fire History', 'Site Notes',
            'Min Temp (°C)', 'Max Temp (°C)', 'Weather Source', 'Weather Station',
            'Auto Weather - Current Temp', 'Auto Weather - Conditions',
            'Auto Weather - Humidity (%)', 'Auto Weather - Wind Speed (km/h)',
            'Auto Weather - Precipitation (mm)'
        ];
        
        // Generate rows
        const rows = records.map(record => {
            const row = [
                record.id,
                record.timestamp,
                record.program,
                record.observer,
                record.collectionDate,
                record.species,
                record.locationMode,
                record.location?.region || '',
                record.location?.siteName || '',
                record.location?.latitude || '',
                record.location?.longitude || '',
                record.phenology?.flowering?.bud || false,
                record.phenology?.flowering?.earlyFlower || false,
                record.phenology?.flowering?.fullFlower || false,
                record.phenology?.flowering?.petalFall || false,
                record.phenology?.flowering?.seedPod || false,
                record.phenology?.flowering?.none || false,
                record.phenology?.pollinators?.honeybee || false,
                record.phenology?.pollinators?.nativeBee || false,
                record.phenology?.pollinators?.fly || false,
                record.phenology?.pollinators?.beetle || false,
                record.phenology?.pollinators?.wasp || false,
                record.phenology?.pollinators?.butterfly || false,
                record.phenology?.pollinators?.birds || false,
                record.phenology?.pollinators?.other || '',
                record.phenology?.pollinators?.none || false,
                record.phenology?.seedMaturity || '',
                record.siteHistory?.fire || '',
                record.siteHistory?.notes || '',
                record.weather?.minTemp || '',
                record.weather?.maxTemp || '',
                record.weather?.dataType || '',
                record.weather?.station || '',
                record.weather?.autoWeather?.current?.temperature || '',
                record.weather?.autoWeather?.current?.weatherDescription || '',
                record.weather?.autoWeather?.current?.humidity || '',
                record.weather?.autoWeather?.current?.windSpeed || '',
                record.weather?.autoWeather?.daily?.precipitation || ''
            ];
            
            // Escape fields that might contain commas or quotes
            return row.map(field => {
                if (typeof field === 'string' && (field.includes(',') || field.includes('"') || field.includes('\n'))) {
                    return `"${field.replace(/"/g, '""')}"`;
                }
                return field;
            }).join(',');
        });
        
        return [headers.join(','), ...rows].join('\n');
    }

    function exportAllCSV() {
        if (savedRecords.length === 0) { 
            alert('No records to export'); 
            return; 
        }
        
        const csvString = generateCSVString(savedRecords);
        downloadCSV(csvString, 'all_records');
    }

    function exportSelectedCSV() {
        if (selectedRecordIds.size === 0) {
            alert('No records selected. Check the boxes on records you want to export.');
            return;
        }
        
        const selectedRecords = savedRecords.filter(record => selectedRecordIds.has(record.id.toString()));
        
        if (selectedRecords.length === 0) {
            alert('Selected records not found');
            return;
        }
        
        const csvString = generateCSVString(selectedRecords);
        downloadCSV(csvString, 'selected_records');
        
        document.getElementById('outputBox').innerText = `✅ Exported ${selectedRecords.length} selected record(s) to CSV`;
    }

    function downloadCSV(csvString, filePrefix) {
        const blob = new Blob([csvString], { type: 'text/csv;charset=utf-8;' });
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = `future_seeds_${filePrefix}_${new Date().toISOString().split('T')[0]}.csv`;
        a.click();
        URL.revokeObjectURL(url);
    }

    // ========== CSV IMPORT ==========
    function importFromCSV() {
        const fileInput = document.getElementById('importFile');
        const file = fileInput.files[0];
        if (!file) return;
        
        if (file.size > 5 * 1024 * 1024) {
            alert('File too large. Maximum size is 5MB.');
            fileInput.value = '';
            return;
        }
        
        const reader = new FileReader();
        reader.onload = function(e) {
            try {
                const csvText = e.target.result;
                const lines = csvText.split('\n');
                const headers = lines[0].split(',').map(h => h.trim());
                
                let importedCount = 0;
                
                for (let i = 1; i < lines.length; i++) {
                    if (!lines[i].trim()) continue;
                    
                    // Simple CSV parsing (handles quoted fields)
                    const values = [];
                    let inQuote = false;
                    let currentValue = '';
                    
                    for (let char of lines[i]) {
                        if (char === '"' && !inQuote) {
                            inQuote = true;
                        } else if (char === '"' && inQuote) {
                            inQuote = false;
                        } else if (char === ',' && !inQuote) {
                            values.push(currentValue);
                            currentValue = '';
                        } else {
                            currentValue += char;
                        }
                    }
                    values.push(currentValue);
                    
                    // Create record object from CSV row
                    if (values.length >= 10) {
                        const record = {
                            id: Date.now() + i + Math.random(),
                            timestamp: new Date().toISOString(),
                            program: "Future Seeds Program (Imported)",
                            observer: values[3] || '',
                            collectionDate: values[4] || '',
                            species: values[5] || '',
                            locationMode: values[6] || 'quick_region',
                            location: {
                                region: values[7] || '',
                                siteName: values[8] || '',
                                latitude: parseFloat(values[9]) || -42.88,
                                longitude: parseFloat(values[10]) || 147.33,
                                locationMode: values[6] || 'quick_region'
                            },
                            phenology: {
                                flowering: {
                                    bud: values[11] === 'true',
                                    earlyFlower: values[12] === 'true',
                                    fullFlower: values[13] === 'true',
                                    petalFall: values[14] === 'true',
                                    seedPod: values[15] === 'true',
                                    none: values[16] === 'true'
                                },
                                pollinators: {
                                    honeybee: values[17] === 'true',
                                    nativeBee: values[18] === 'true',
                                    fly: values[19] === 'true',
                                    beetle: values[20] === 'true',
                                    wasp: values[21] === 'true',
                                    butterfly: values[22] === 'true',
                                    birds: values[23] === 'true',
                                    other: values[24] || '',
                                    none: values[25] === 'true'
                                },
                                seedMaturity: values[26] || ''
                            },
                            siteHistory: {
                                fire: values[27] || '',
                                notes: values[28] || ''
                            },
                            weather: {
                                minTemp: parseFloat(values[29]) || null,
                                maxTemp: parseFloat(values[30]) || null,
                                dataType: values[31] || 'Imported',
                                station: values[32] || ''
                            }
                        };
                        
                        savedRecords.push(record);
                        importedCount++;
                    }
                }
                
                if (importedCount > 0) {
                    localStorage.setItem(STORAGE_KEY, JSON.stringify(savedRecords));
                    displayRecords();
                    updateStats();
                    updateStorageMeter();
                    document.getElementById('outputBox').innerText = `✅ Imported ${importedCount} records from CSV`;
                } else {
                    alert('No valid records found in CSV');
                }
                
                fileInput.value = '';
                
            } catch (error) {
                console.error('Import error:', error);
                alert('Error importing CSV: ' + error.message);
            }
        };
        
        reader.readAsText(file);
    }

    function toggleRecordSelection(id, checked) {
        const idStr = id.toString();
        if (checked) {
            selectedRecordIds.add(idStr);
        } else {
            selectedRecordIds.delete(idStr);
        }
        // Update UI to show selection count
        const count = selectedRecordIds.size;
        if (count > 0) {
            document.getElementById('outputBox').innerText = `✅ ${count} record(s) selected for export`;
        }
    }

    function displayRecords() {
        const grid = document.getElementById('recordsGrid');
        const countEl = document.getElementById('recordCount');
        
        if (!savedRecords || savedRecords.length === 0) {
            grid.innerHTML = '<div style="grid-column:1/-1; text-align:center; padding:2rem; color:#5f7344;">No saved records yet. Complete and save your first observation!</div>';
            countEl.innerText = '0 records';
            selectedRecordIds.clear();
            return;
        }

        countEl.innerText = `${savedRecords.length} record${savedRecords.length !== 1 ? 's' : ''}`;
        const sortedRecords = [...savedRecords].sort((a, b) => new Date(b.collectionDate) - new Date(a.collectionDate));
        
        grid.innerHTML = sortedRecords.map((record) => {
            const weatherSource = record.weather && record.weather.dataType === "Open-Meteo Auto" ? " (auto)" : "";
            const displaySpecies = record.species ? record.species.split(' ').slice(0, 2).join(' ') : 'Unknown';
            const locationIcon = record.location.locationMode === 'precise_map' ? '🗺️' : '📍';
            const locationDisplay = record.location.locationMode === 'precise_map' 
                ? (record.location.siteName || 'Map pin') 
                : record.location.region.split(' ')[0];
            
            // Count pollinators (including birds)
            const pollinatorCount = Object.entries(record.phenology?.pollinators || {})
                .filter(([key, value]) => value && key !== 'other' && key !== 'none').length;
            
            const isSelected = selectedRecordIds.has(record.id.toString());
            
            return `
                <div class="record-card" data-id="${record.id}" onclick="selectRecord('${record.id}')">
                    <input type="checkbox" class="record-select" ${isSelected ? 'checked' : ''} onclick="event.stopPropagation(); toggleRecordSelection('${record.id}', this.checked)">
                    <div class="record-date">📅 ${record.collectionDate}</div>
                    <div class="record-species">🌿 <i>${displaySpecies}</i></div>
                    <div class="record-location">${locationIcon} ${locationDisplay}</div>
                    ${record.weather && record.weather.minTemp && record.weather.maxTemp ? 
                        `<div class="record-weather">🌡️ ${record.weather.minTemp}°C / ${record.weather.maxTemp}°C${weatherSource}</div>` : ''}
                    <div class="record-weather">🐝 Pollinators: ${pollinatorCount}</div>
                    <div class="record-actions">
                        <button class="record-btn edit" onclick="event.stopPropagation(); editRecord('${record.id}')">✏️ Edit</button>
                        <button class="record-btn delete" onclick="event.stopPropagation(); deleteRecord('${record.id}')">🗑️ Delete</button>
                    </div>
                </div>
            `;
        }).join('');
    }

    function selectRecord(id) {
        const record = savedRecords.find(r => r.id == id);
        if (!record) return;
        const displayRecord = {...record};
        document.getElementById('outputBox').innerText = JSON.stringify(displayRecord, null, 2);
        document.querySelectorAll('.record-card').forEach(c => c.classList.remove('selected'));
        const selectedCard = document.querySelector(`.record-card[data-id="${id}"]`);
        if (selectedCard) selectedCard.classList.add('selected');
    }

    function editRecord(id) {
        const record = savedRecords.find(r => r.id == id);
        if (!record) return;
        
        document.getElementById('observer').value = record.observer;
        document.getElementById('obsDate').value = record.collectionDate;
        document.getElementById('siteName').value = record.location.siteName || '';
        document.getElementById('lat').value = record.location.latitude;
        document.getElementById('lon').value = record.location.longitude;
        document.getElementById('coordSource').value = record.location.coordinateSource || '';
        document.getElementById('speciesSelect').value = record.species;
        updateSpeciesInfo();
        
        if (record.location.locationMode === 'quick_region') {
            for (const [code, preset] of Object.entries(regionPresets)) {
                if (preset.name === record.location.region) {
                    document.getElementById('regionSelect').value = code;
                    break;
                }
            }
        } else {
            document.getElementById('regionSelect').value = 'south';
        }
        
        document.getElementById('bud').checked = record.phenology.flowering.bud;
        document.getElementById('earlyFlower').checked = record.phenology.flowering.earlyFlower;
        document.getElementById('fullFlower').checked = record.phenology.flowering.fullFlower;
        document.getElementById('petalFall').checked = record.phenology.flowering.petalFall;
        document.getElementById('seedPod').checked = record.phenology.flowering.seedPod;
        document.getElementById('floweringNone').checked = record.phenology.flowering.none || false;
        
        document.getElementById('honeybee').checked = record.phenology.pollinators.honeybee;
        document.getElementById('nativeBee').checked = record.phenology.pollinators.nativeBee;
        document.getElementById('fly').checked = record.phenology.pollinators.fly;
        document.getElementById('beetle').checked = record.phenology.pollinators.beetle;
        document.getElementById('wasp').checked = record.phenology.pollinators.wasp;
        document.getElementById('butterfly').checked = record.phenology.pollinators.butterfly;
        document.getElementById('birds').checked = record.phenology.pollinators.birds || false;
        document.getElementById('otherPollinators').value = record.phenology.pollinators.other || '';
        document.getElementById('pollinatorsNone').checked = record.phenology.pollinators.none || false;
        
        document.getElementById('actualMinTemp').value = record.weather.minTemp || '';
        document.getElementById('actualMaxTemp').value = record.weather.maxTemp || '';
        document.getElementById('bomStation').value = record.weather.station || '';
        document.getElementById('stationId').value = record.weather.stationId || '';
        
        if (record.weather.autoWeather) {
            lastWeatherData = record.weather.autoWeather;
        }
        
        document.getElementById('seedMaturity').value = record.phenology.seedMaturity || '';
        document.getElementById('fireHistory').value = record.siteHistory.fire || '';
        document.getElementById('notes').value = record.siteHistory.notes || '';
        
        updateMonthDisplay();
        updateTempDisplay();
        
        if (marker) {
            marker.setLatLng([record.location.latitude, record.location.longitude]);
            map.setView([record.location.latitude, record.location.longitude], 8);
        }
        
        if (record.locationMode === 'precise_map') enableMapMode();
        else enableQuickRegionMode();
        
        document.getElementById('outputBox').innerText = `✏️ Editing record from ${record.collectionDate}`;
        deleteRecord(id, true);
    }

    function deleteRecord(id, silent = false) {
        const index = savedRecords.findIndex(r => r.id == id);
        if (index === -1) return;
        if (!silent && !confirm('Delete this record?')) return;
        
        // Remove from selected set if present
        selectedRecordIds.delete(id.toString());
        
        savedRecords.splice(index, 1);
        localStorage.setItem(STORAGE_KEY, JSON.stringify(savedRecords));
        displayRecords();
        updateStats();
        updateStorageMeter();
        if (!silent) document.getElementById('outputBox').innerText = '🗑️ Record deleted.';
    }

    function clearAllRecords() {
        if (confirm('Delete ALL saved records?')) {
            savedRecords = [];
            selectedRecordIds.clear();
            localStorage.removeItem(STORAGE_KEY);
            displayRecords();
            updateStats();
            updateStorageMeter();
            document.getElementById('outputBox').innerText = '🗑️ All records cleared.';
        }
    }

    function updateStats() {
        document.getElementById('totalRecordsStat').innerText = savedRecords.length;
        if (savedRecords.length > 0) {
            const temps = savedRecords.filter(r => r.weather && r.weather.minTemp && r.weather.maxTemp);
            if (temps.length > 0) {
                const avgMin = temps.reduce((sum, r) => sum + r.weather.minTemp, 0) / temps.length;
                const avgMax = temps.reduce((sum, r) => sum + r.weather.maxTemp, 0) / temps.length;
                document.getElementById('avgTempStat').innerHTML = `${avgMin.toFixed(1)}/${avgMax.toFixed(1)}°C`;
            } else {
                document.getElementById('avgTempStat').innerHTML = 'No temps';
            }
        }
    }

    function resetForm() {
        const currentObserver = document.getElementById('observer').value.trim();
        
        // Set today's date in YYYY-MM-DD format
        const today = new Date();
        const year = today.getFullYear();
        const month = String(today.getMonth() + 1).padStart(2, '0');
        const day = String(today.getDate()).padStart(2, '0');
        const todayStr = `${year}-${month}-${day}`;
        
        document.getElementById('obsDate').value = todayStr;
        document.getElementById('siteName').value = '';
        document.getElementById('lat').value = '-42.88';
        document.getElementById('lon').value = '147.33';
        document.getElementById('coordSource').value = 'Quick Region (South (Hobart))';
        document.getElementById('bud').checked = false;
        document.getElementById('earlyFlower').checked = false;
        document.getElementById('fullFlower').checked = false;
        document.getElementById('petalFall').checked = false;
        document.getElementById('seedPod').checked = false;
        document.getElementById('floweringNone').checked = false;
        document.getElementById('honeybee').checked = false;
        document.getElementById('nativeBee').checked = false;
        document.getElementById('fly').checked = false;
        document.getElementById('beetle').checked = false;
        document.getElementById('wasp').checked = false;
        document.getElementById('butterfly').checked = false;
        document.getElementById('birds').checked = false;
        document.getElementById('pollinatorsNone').checked = false;
        document.getElementById('otherPollinators').value = '';
        document.getElementById('actualMinTemp').value = '';
        document.getElementById('actualMaxTemp').value = '';
        document.getElementById('bomStation').value = '';
        document.getElementById('stationId').value = '';
        document.getElementById('seedMaturity').value = '';
        document.getElementById('fireHistory').value = '';
        document.getElementById('notes').value = '';
        document.getElementById('speciesSelect').value = 'Acacia verticillata';
        document.getElementById('regionSelect').value = 'south';
        
        if (currentObserver) {
            document.getElementById('observer').value = currentObserver;
            localStorage.setItem(OBSERVER_KEY, currentObserver);
            savedObserver = currentObserver;
        } else if (savedObserver) {
            document.getElementById('observer').value = savedObserver;
        }
        
        lastWeatherData = null;
        
        updateSpeciesInfo();
        updateMonthDisplay();
        updateTempDisplay();
        document.getElementById('warningsPanel').style.display = 'none';
        enableQuickRegionMode();
        
        if (marker) {
            marker.setLatLng([-42.88, 147.33]);
            map.setView([-42.88, 147.33], 7);
        }
    }

    // Event listeners for checkboxes
    document.addEventListener('DOMContentLoaded', function() {
        const floweringCheckboxes = ['bud', 'earlyFlower', 'fullFlower', 'petalFall', 'seedPod'];
        floweringCheckboxes.forEach(id => {
            document.getElementById(id).addEventListener('change', function() {
                if (this.checked) document.getElementById('floweringNone').checked = false;
            });
        });

        const pollinatorCheckboxes = ['honeybee', 'nativeBee', 'fly', 'beetle', 'wasp', 'butterfly', 'birds'];
        pollinatorCheckboxes.forEach(id => {
            document.getElementById(id).addEventListener('change', function() {
                if (this.checked) document.getElementById('pollinatorsNone').checked = false;
            });
        });

        document.getElementById('otherPollinators').addEventListener('input', function() {
            if (this.value.trim() !== '') document.getElementById('pollinatorsNone').checked = false;
        });
    });

    // Initialize on load
    window.onload = function() {
        initMap();
        initializeEnhancedSpeciesSelector();
        
        // Set today's date as default
        const today = new Date();
        const year = today.getFullYear();
        const month = String(today.getMonth() + 1).padStart(2, '0');
        const day = String(today.getDate()).padStart(2, '0');
        document.getElementById('obsDate').value = `${year}-${month}-${day}`;
        
        updateSpeciesInfo();
        updateMonthDisplay();
        updateTempDisplay();
        displayRecords();
        updateStats();
        updateStorageMeter();
        enableQuickRegionMode();
        updateFromRegion();
        if (savedObserver) document.getElementById('observer').value = savedObserver;
        if (savedRecords.length > 0) document.getElementById('outputBox').innerText = `📊 Welcome back! You have ${savedRecords.length} saved record(s).`;
        
        // Hide photo elements via CSS
        const style = document.createElement('style');
        style.innerHTML = `
            .photo-section, .camera-note, #photoCount, #photoPreview, 
            [onclick*="openCamera"], [onclick*="clearAllPhotos"],
            button[onclick*="openCamera"], button[onclick*="clearAllPhotos"] {
                display: none !important;
            }
        `;
        document.head.appendChild(style);
    };

/* --- Event Listeners --- */

// User Guide toggle
document.getElementById('divine-handler-onclick-1773285837194-0').addEventListener('click', function(event) {
  toggleGuide()
});

// Location mode toggle
document.getElementById('toggleLocationMode').addEventListener('click', function(event) {
  toggleLocationMode()
});

// My Location button
document.getElementById('divine-handler-onclick-1773285837194-2').addEventListener('click', function(event) {
  getUserLocation()
});

// Show map button
document.getElementById('showMapBtn').addEventListener('click', function(event) {
  toggleMap(true)
});

// Hide map button
document.getElementById('hideMapBtn').addEventListener('click', function(event) {
  toggleMap(false)
});

// Flowering None checkbox
document.getElementById('floweringNone').addEventListener('click', function(event) {
  handleFloweringNone()
});

// Pollinators None checkbox
document.getElementById('pollinatorsNone').addEventListener('click', function(event) {
  handlePollinatorsNone()
});

// Auto weather button
document.getElementById('autoWeatherBtn').addEventListener('click', function(event) {
  loadCurrentWeather(true)
});

// Reset button
document.getElementById('divine-handler-onclick-1773285837194-11').addEventListener('click', function(event) {
  resetForm()
});

// Save Record button
document.getElementById('divine-handler-onclick-1773285837194-12').addEventListener('click', function(event) {
  saveRecord()
});

// Email CSV button
document.getElementById('emailCsvBtn').addEventListener('click', function(event) {
  emailDataAsCSV()
});

// Export All CSV button
document.getElementById('exportCsvBtn').addEventListener('click', function(event) {
  exportAllCSV()
});

// Export Selected CSV button
document.getElementById('exportSelectedCsvBtn').addEventListener('click', function(event) {
  exportSelectedCSV()
});

// Clear All button
document.getElementById('divine-handler-onclick-1773285837194-17').addEventListener('click', function(event) {
  clearAllRecords()
});

// Species change
document.getElementById('speciesSelect').addEventListener('change', function(event) {
  updateSpeciesInfo()
});

// Region change
document.getElementById('regionSelect').addEventListener('change', function(event) {
  updateFromRegion()
});

// Date change
document.getElementById('obsDate').addEventListener('change', function(event) {
  updateMonthDisplay()
});

// Import CSV file change
document.getElementById('importFile').addEventListener('change', function(event) {
  importFromCSV()
});

// Make functions globally available for onclick handlers
window.toggleRecordSelection = toggleRecordSelection;
window.selectRecord = selectRecord;
window.editRecord = editRecord;
window.deleteRecord = deleteRecord;
