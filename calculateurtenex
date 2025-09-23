<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tenex - Calculateur d'économies</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .header {
            text-align: center;
            color: white;
            margin-bottom: 30px;
            animation: fadeIn 0.6s ease-out;
        }
        
        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            font-weight: 700;
        }
        
        .header p {
            font-size: 1.2rem;
            opacity: 0.95;
        }
        
        .main-card {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            animation: slideUp 0.8s ease-out;
        }
        
        .company-selector {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 15px;
            margin-bottom: 40px;
        }
        
        .company-btn {
            padding: 20px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            background: white;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
        }
        
        .company-btn:hover {
            border-color: #667eea;
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.1);
        }
        
        .company-btn.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: transparent;
        }
        
        .company-btn h3 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }
        
        .company-btn p {
            font-size: 0.85rem;
            opacity: 0.8;
        }
        
        .parameters {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
            padding: 30px;
            background: #f8f9fa;
            border-radius: 15px;
        }
        
        .param-group {
            display: flex;
            flex-direction: column;
        }
        
        .param-group label {
            font-weight: 600;
            margin-bottom: 8px;
            color: #334155;
            font-size: 0.9rem;
        }
        
        .param-group input {
            padding: 12px;
            border: 2px solid #e2e8f0;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .param-group input:focus {
            outline: none;
            border-color: #667eea;
        }
        
        .param-group .info {
            font-size: 0.8rem;
            color: #64748b;
            margin-top: 5px;
        }
        
        .comparison {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .comparison-card {
            padding: 30px;
            border-radius: 15px;
            position: relative;
            overflow: hidden;
        }
        
        .comparison-card.agency {
            background: linear-gradient(135deg, #ff6b6b 0%, #ee5a24 100%);
            color: white;
        }
        
        .comparison-card.tenex {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        
        .comparison-card h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
        }
        
        .cost-breakdown {
            margin-bottom: 20px;
        }
        
        .cost-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding: 10px 0;
            border-bottom: 1px solid rgba(255,255,255,0.2);
        }
        
        .total-cost {
            font-size: 2.5rem;
            font-weight: bold;
            margin-top: 20px;
        }
        
        .savings-highlight {
            background: linear-gradient(135deg, #10b981 0%, #059669 100%);
            color: white;
            padding: 50px;
            border-radius: 20px;
            text-align: center;
            margin-bottom: 50px;
            box-shadow: 0 20px 40px rgba(16, 185, 129, 0.3);
            animation: pulse 3s infinite;
        }
        
        .savings-amount {
            font-size: 4rem;
            font-weight: bold;
            margin-bottom: 15px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }
        
        .savings-percent {
            font-size: 1.8rem;
            opacity: 0.95;
            margin-bottom: 10px;
        }
        
        .savings-subtitle {
            font-size: 1rem;
            opacity: 0.8;
            font-weight: 300;
        }
        
        .equivalent-commission {
            background: linear-gradient(135deg, #f59e0b 0%, #ea580c 100%);
            color: white;
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            margin-bottom: 30px;
        }
        
        .equivalent-commission h3 {
            font-size: 1.1rem;
            margin-bottom: 10px;
            opacity: 0.95;
        }
        
        .commission-value {
            font-size: 2.5rem;
            font-weight: bold;
        }
        
        .recommended-plan {
            background: #f0f9ff;
            border-left: 4px solid #667eea;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 30px;
        }
        
        .recommended-plan h3 {
            color: #667eea;
            margin-bottom: 10px;
        }
        
        .plan-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }
        
        .plan-detail {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .plan-detail::before {
            content: "✓";
            color: #10b981;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .tooltip {
            position: relative;
            display: inline-block;
            cursor: help;
        }
        
        .tooltip .tooltiptext {
            visibility: hidden;
            width: 200px;
            background-color: #333;
            color: #fff;
            text-align: center;
            border-radius: 6px;
            padding: 8px;
            position: absolute;
            z-index: 1;
            bottom: 125%;
            left: 50%;
            margin-left: -100px;
            opacity: 0;
            transition: opacity 0.3s;
            font-size: 0.8rem;
        }
        
        .tooltip:hover .tooltiptext {
            visibility: visible;
            opacity: 1;
        }
        
        .section-divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, #e2e8f0, transparent);
            margin: 40px 0;
        }
        
        tr:hover {
            background: #f8f9fa;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes slideUp {
            from { opacity: 0; transform: translateY(40px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); box-shadow: 0 20px 40px rgba(16, 185, 129, 0.3); }
            50% { transform: scale(1.02); box-shadow: 0 25px 50px rgba(16, 185, 129, 0.4); }
            100% { transform: scale(1); box-shadow: 0 20px 40px rgba(16, 185, 129, 0.3); }
        }
        
        .sensitivity-table {
            overflow-x: auto;
            margin-bottom: 40px;
        }
        
        .sensitivity-table h3 {
            margin-bottom: 20px;
            color: #334155;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 10px;
            overflow: hidden;
        }
        
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }
        
        td {
            padding: 15px;
            border-bottom: 1px solid #e2e8f0;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🚀 Tenex - Calculateur d'économies</h1>
            <p>Découvrez combien vous économisez par rapport aux méthodes de recrutement traditionnelles</p>
        </div>
        
        <div class="main-card">
            <h2 style="margin-bottom: 30px; color: #334155;">Sélectionnez votre type d'entreprise</h2>
            
            <div class="company-selector">
                <div class="company-btn" data-type="tpe">
                    <h3>TPE</h3>
                    <p>1 à 9 salariés</p>
                </div>
                <div class="company-btn" data-type="petite-pme">
                    <h3>Petite PME</h3>
                    <p>10 à 49 salariés</p>
                </div>
                <div class="company-btn" data-type="moyenne-pme">
                    <h3>Moyenne PME</h3>
                    <p>50 à 249 salariés</p>
                </div>
                <div class="company-btn" data-type="eti">
                    <h3>ETI</h3>
                    <p>250 à 4999 salariés</p>
                </div>
                <div class="company-btn" data-type="grande">
                    <h3>Grande entreprise</h3>
                    <p>5000+ salariés</p>
                </div>
                <div class="company-btn" data-type="startup">
                    <h3>Startup</h3>
                    <p>Croissance rapide</p>
                </div>
            </div>
            
            <div class="parameters" id="parameters" style="display: none;">
                <div class="param-group">
                    <label>Nombre de postes à pourvoir par an</label>
                    <input type="number" id="jobsCount" min="1" value="5">
                    <span class="info">Modifiable selon vos besoins réels</span>
                </div>
                <div class="param-group">
                    <label>Salaire moyen des postes (€/an)</label>
                    <input type="number" id="avgSalary" value="45000">
                    <span class="info">Brut annuel moyen</span>
                </div>
                <div class="param-group" style="grid-column: span 2;">
                    <label style="display: flex; align-items: center; gap: 10px; cursor: pointer;">
                        <input type="checkbox" id="useCabinet" style="width: auto; transform: scale(1.2);">
                        <span>Nous passons par un cabinet de recrutement</span>
                    </label>
                    <span class="info">Cochez si vous utilisez actuellement des cabinets de recrutement</span>
                </div>
                <div class="param-group" id="cabinetParams" style="display: none;">
                    <label>Commission cabinet (%)</label>
                    <input type="number" id="agencyCommission" value="18" min="10" max="25">
                    <span class="info">Généralement 15-20%</span>
                </div>
                <div class="param-group" id="jobboardParams">
                    <label>
                        Coût par recrutement avec jobboards (€)
                        <span class="tooltip">❓
                            <span class="tooltiptext">Coût moyen d'une annonce + accès CVthèque sur les sites emploi</span>
                        </span>
                    </label>
                    <input type="number" id="jobboardCost" value="1000">
                    <span class="info">Annonce + CVthèque (adapté selon votre taille)</span>
                </div>
                <div class="param-group">
                    <label>Équipe RH dédiée au recrutement</label>
                    <input type="number" id="hrCount" value="1" min="0">
                    <span class="info">Nombre de personnes impliquées</span>
                </div>
                <div class="param-group">
                    <label>
                        Coût horaire équipe RH (€/h)
                        <span class="tooltip">❓
                            <span class="tooltiptext">Salaire + charges sociales + coûts indirects</span>
                        </span>
                    </label>
                    <input type="number" id="hrRate" value="25">
                    <span class="info">Coût horaire tout compris</span>
                </div>
                <div class="param-group" id="timePerHireGroup">
                    <label>Temps consacré par recrutement (h)</label>
                    <input type="number" id="timePerHire" value="20">
                    <span class="info">Sourcing + entretiens + suivi</span>
                </div>
            </div>
            
            <div id="results" style="display: none;">
                <div class="savings-highlight" id="savingsHighlight">
                    <div class="savings-amount" id="savingsAmount">0 €</div>
                    <div class="savings-percent" id="savingsPercent">0% d'économies</div>
                    <div class="savings-subtitle">d'économies par rapport à votre méthode actuelle</div>
                </div>
                
                <div class="recommended-plan" id="recommendedPlan"></div>
                
                <div class="section-divider"></div>
                
                <div class="comparison">
                    <div class="comparison-card agency">
                        <h3 id="currentMethodTitle">🏢 Méthode actuelle</h3>
                        <div class="cost-breakdown" id="currentMethodCosts"></div>
                        <div class="total-cost" id="currentMethodTotal">0 €</div>
                    </div>
                    <div class="comparison-card tenex">
                        <h3>✨ Tenex</h3>
                        <div class="cost-breakdown" id="tenexCosts"></div>
                        <div class="total-cost" id="tenexTotal">0 €</div>
                    </div>
                </div>
                
                <div class="section-divider"></div>
                
                <div class="equivalent-commission">
                    <h3>Votre abonnement Tenex équivaut à une commission de</h3>
                    <div class="commission-value" id="equivalentCommission">0%</div>
                </div>
                
                <div class="sensitivity-table">
                    <h3>📊 Simulation selon le nombre de recrutements annuels</h3>
                    <table>
                        <thead>
                            <tr>
                                <th>Recrutements/an</th>
                                <th>Plan Tenex</th>
                                <th id="currentMethodHeader">Coût actuel</th>
                                <th>Coût Tenex</th>
                                <th>Économies</th>
                                <th>% économisé</th>
                            </tr>
                        </thead>
                        <tbody id="sensitivityTableBody"></tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        const companyProfiles = {
            'tpe': { jobs: 2, avgSalary: 35000, commission: 18, hrCount: 0, hrRate: 60, timePerHire: 20, jobboardCost: 1300 },
            'petite-pme': { jobs: 4, avgSalary: 40000, commission: 18, hrCount: 1, hrRate: 20, timePerHire: 20, jobboardCost: 1100 },
            'moyenne-pme': { jobs: 8, avgSalary: 45000, commission: 17, hrCount: 1, hrRate: 22, timePerHire: 20, jobboardCost: 1000 },
            'eti': { jobs: 20, avgSalary: 50000, commission: 16, hrCount: 3, hrRate: 25, timePerHire: 20, jobboardCost: 900 },
            'grande': { jobs: 50, avgSalary: 55000, commission: 15, hrCount: 8, hrRate: 30, timePerHire: 20, jobboardCost: 800 },
            'startup': { jobs: 12, avgSalary: 48000, commission: 20, hrCount: 1, hrRate: 40, timePerHire: 20, jobboardCost: 1200 }
        };
        
        const tenexPlans = [
            { name: 'TPE Pay-per-use', price: 149, maxJobs: 1, isPerJob: true, features: ['149€ par annonce', 'Matching intelligent', 'Support inclus'] },
            { name: 'Core', price: 249, maxJobs: 3, features: ['3 postes actifs', 'Matching intelligent', 'Intégrations ATS'] },
            { name: 'Premium', price: 449, maxJobs: 5, features: ['5 postes actifs', 'IA personnalisée', 'Multi-utilisateurs'] },
            { name: 'Premium Plus', price: 799, maxJobs: 10, features: ['10 postes actifs', 'Priorité matching', 'Analytics avancés'] },
            { name: 'Grands Comptes', price: null, maxJobs: Infinity, features: ['Postes illimités', 'CSM dédié', 'Intégration complète'] }
        ];
        
        let selectedCompany = null;
        
        // Company selection
        document.querySelectorAll('.company-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                document.querySelectorAll('.company-btn').forEach(b => b.classList.remove('active'));
                this.classList.add('active');
                
                selectedCompany = this.dataset.type;
                const profile = companyProfiles[selectedCompany];
                
                // Fill form values
                document.getElementById('jobsCount').value = profile.jobs;
                document.getElementById('avgSalary').value = profile.avgSalary;
                document.getElementById('agencyCommission').value = profile.commission;
                document.getElementById('jobboardCost').value = profile.jobboardCost;
                document.getElementById('hrCount').value = profile.hrCount;
                document.getElementById('hrRate').value = profile.hrRate;
                document.getElementById('timePerHire').value = profile.timePerHire;
                
                // Set checkbox based on company type
                document.getElementById('useCabinet').checked = selectedCompany !== 'tpe';
                
                // Show parameters and update display
                document.getElementById('parameters').style.display = 'grid';
                toggleCabinetParams();
                calculate();
            });
        });
        
        // Cabinet checkbox toggle
        document.getElementById('useCabinet').addEventListener('change', function() {
            toggleCabinetParams();
            calculate();
        });
        
        function toggleCabinetParams() {
            const useCabinet = document.getElementById('useCabinet').checked;
            const cabinetParams = document.getElementById('cabinetParams');
            const jobboardParams = document.getElementById('jobboardParams');
            const timePerHireGroup = document.getElementById('timePerHireGroup');
            
            if (useCabinet) {
                cabinetParams.style.display = 'flex';
                jobboardParams.style.display = 'none';
                timePerHireGroup.style.display = 'none';
            } else {
                cabinetParams.style.display = 'none';
                jobboardParams.style.display = 'flex';
                timePerHireGroup.style.display = 'flex';
            }
        }
        
        // Input listeners
        document.querySelectorAll('#parameters input').forEach(input => {
            input.addEventListener('input', calculate);
        });
        
        function selectPlan(jobs) {
            // Pour les TPE : comparer pay-per-use vs abonnement mensuel
            const payPerUseCost = jobs * 149; // 149€ par annonce
            const coreAnnualCost = 249 * 12; // 2988€ par an
            
            // Si pay-per-use moins cher OU TPE avec peu de recrutements, utiliser pay-per-use
            if (payPerUseCost < coreAnnualCost || (selectedCompany === 'tpe' && jobs <= 4)) {
                return tenexPlans.find(p => p.name === 'TPE Pay-per-use');
            }
            
            // Sinon, logique normale par postes simultanés
            const monthlyJobs = Math.ceil(jobs / 4);
            
            if (monthlyJobs <= 3) return tenexPlans.find(p => p.name === 'Core');
            if (monthlyJobs <= 5) return tenexPlans.find(p => p.name === 'Premium');
            if (monthlyJobs <= 10) return tenexPlans.find(p => p.name === 'Premium Plus');
            
            return tenexPlans.find(p => p.name === 'Grands Comptes');
        }
        
        function calculate() {
            const jobs = parseInt(document.getElementById('jobsCount').value) || 0;
            const avgSalary = parseInt(document.getElementById('avgSalary').value) || 0;
            const commission = parseFloat(document.getElementById('agencyCommission').value) || 0;
            const jobboardCost = parseFloat(document.getElementById('jobboardCost').value) || 0;
            const hrRate = parseFloat(document.getElementById('hrRate').value) || 0;
            const timePerHire = parseFloat(document.getElementById('timePerHire').value) || 0;
            const useCabinet = document.getElementById('useCabinet').checked;
            
            if (jobs === 0) return;
            
            console.log('Début calcul:', { jobs, avgSalary, useCabinet, commission, jobboardCost, hrRate, timePerHire });
            
            // Current method costs
            let currentMethodTotal = 0;
            let currentMethodCostsHTML = '';
            
            if (useCabinet) {
                const commissionCost = jobs * avgSalary * (commission / 100);
                currentMethodTotal = commissionCost;
                currentMethodCostsHTML = `
                    <div class="cost-item">
                        <span>Commissions cabinet (${commission}%)</span>
                        <span>${commissionCost.toLocaleString('fr-FR')} €</span>
                    </div>
                    <div class="cost-item">
                        <span style="opacity: 0.6;">Coûts RH (gérés par le cabinet)</span>
                        <span style="opacity: 0.6;">-</span>
                    </div>
                `;
            } else {
                const jobboardTotal = jobs * jobboardCost;
                const hrCost = jobs * timePerHire * hrRate;
                currentMethodTotal = jobboardTotal + hrCost;
                currentMethodCostsHTML = `
                    <div class="cost-item">
                        <span>Jobboards (${jobboardCost.toLocaleString('fr-FR')} €/poste)</span>
                        <span>${jobboardTotal.toLocaleString('fr-FR')} €</span>
                    </div>
                    <div class="cost-item">
                        <span>Coûts RH internes</span>
                        <span>${hrCost.toLocaleString('fr-FR')} €</span>
                    </div>
                `;
            }
            
            // Tenex costs
            const selectedPlan = selectPlan(jobs);
            
            let tenexSubscription;
            if (selectedPlan.isPerJob) {
                // Modèle pay-per-use : prix par annonce
                tenexSubscription = jobs * selectedPlan.price;
            } else if (selectedPlan.price === null) {
                // Grands comptes : tarification sur mesure
                tenexSubscription = Math.max(1500, jobs * 150);
            } else {
                // Abonnement mensuel classique
                tenexSubscription = selectedPlan.price * 12;
            }
            
            const tenexHrCost = jobs * (useCabinet ? 5 : timePerHire) * hrRate;
            const tenexTotal = tenexSubscription + tenexHrCost;
            
            // Savings calculation
            const savings = currentMethodTotal - tenexTotal;
            const savingsPercent = currentMethodTotal > 0 ? (savings / currentMethodTotal * 100).toFixed(1) : 0;
            
            console.log('Calculs:', { currentMethodTotal, tenexTotal, savings, savingsPercent });
            
            // Update UI
            document.getElementById('currentMethodTitle').textContent = 
                useCabinet ? '🏢 Cabinet de recrutement' : '🏢 Recrutement interne + Jobboards';
            document.getElementById('currentMethodHeader').textContent = 
                useCabinet ? 'Coût Cabinet' : 'Coût Interne + Jobboards';
            
            document.getElementById('recommendedPlan').innerHTML = `
                <h3>📌 Plan recommandé : ${selectedPlan.name}</h3>
                <p>
                    ${selectedPlan.isPerJob 
                        ? `${selectedPlan.price} € par annonce (${tenexSubscription.toLocaleString('fr-FR')} € pour ${jobs} recrutements)`
                        : selectedPlan.price === null 
                            ? 'Tarif sur mesure' 
                            : selectedPlan.price + ' €/mois'
                    }
                </p>
                <div class="plan-details">
                    ${selectedPlan.features.map(f => `<div class="plan-detail">${f}</div>`).join('')}
                </div>
                <div style="margin-top: 15px; padding: 10px; background: #f0f9ff; border-radius: 8px; font-size: 0.9rem; color: #1e40af;">
                    💡 <strong>Bon à savoir :</strong> ${selectedPlan.isPerJob 
                        ? 'Perfect pour les TPE avec peu de recrutements. Un plan Starter gratuit existe aussi pour tester.'
                        : 'Un plan pay-per-use à 149€/annonce existe pour les entreprises avec moins de 4 recrutements/an.'
                    }
                </div>
            `;
            
            document.getElementById('currentMethodCosts').innerHTML = currentMethodCostsHTML;
            document.getElementById('tenexCosts').innerHTML = `
                <div class="cost-item">
                    <span>Abonnement annuel</span>
                    <span>${tenexSubscription.toLocaleString('fr-FR')} €</span>
                </div>
                <div class="cost-item">
                    <span>Coûts RH internes ${useCabinet ? '(validation/suivi)' : ''}</span>
                    <span>${tenexHrCost.toLocaleString('fr-FR')} €</span>
                </div>
                <div class="cost-item">
                    <span style="opacity: 0.6;">Jobboards (inclus)</span>
                    <span style="opacity: 0.6;">-</span>
                </div>
            `;
            
            document.getElementById('currentMethodTotal').textContent = currentMethodTotal.toLocaleString('fr-FR') + ' €';
            document.getElementById('tenexTotal').textContent = tenexTotal.toLocaleString('fr-FR') + ' €';
            
            // Update savings
            const savingsHighlight = document.getElementById('savingsHighlight');
            document.getElementById('savingsAmount').textContent = savings.toLocaleString('fr-FR') + ' €';
            
            if (savings > 0) {
                savingsHighlight.style.background = 'linear-gradient(135deg, #10b981 0%, #059669 100%)';
                document.getElementById('savingsPercent').textContent = savingsPercent + '% d\'économies';
            } else {
                savingsHighlight.style.background = 'linear-gradient(135deg, #ef4444 0%, #dc2626 100%)';
                document.getElementById('savingsPercent').textContent = Math.abs(savingsPercent) + '% de coût supplémentaire';
            }
            
            // Equivalent commission
            const equivalentCommission = (jobs * avgSalary) > 0 ? 
                (tenexSubscription / (jobs * avgSalary) * 100).toFixed(2) : 0;
            document.getElementById('equivalentCommission').textContent = equivalentCommission + '%';
            
            // Generate sensitivity table
            generateSensitivityTable();
            
            document.getElementById('results').style.display = 'block';
            console.log('Affichage mis à jour');
        }
        
        function generateSensitivityTable() {
            const tbody = document.getElementById('sensitivityTableBody');
            tbody.innerHTML = '';
            
            const jobs = parseInt(document.getElementById('jobsCount').value) || 0;
            const avgSalary = parseInt(document.getElementById('avgSalary').value) || 0;
            const commission = parseFloat(document.getElementById('agencyCommission').value) || 0;
            const jobboardCost = parseFloat(document.getElementById('jobboardCost').value) || 0;
            const hrRate = parseFloat(document.getElementById('hrRate').value) || 0;
            const timePerHire = parseFloat(document.getElementById('timePerHire').value) || 0;
            const useCabinet = document.getElementById('useCabinet').checked;
            
            // Générer seulement 5 lignes pertinentes autour de la valeur actuelle
            let jobsVariations = [];
            
            if (jobs <= 2) {
                jobsVariations = [1, 2, 3, 5, 8];
            } else if (jobs <= 5) {
                jobsVariations = [Math.max(1, jobs-2), Math.max(1, jobs-1), jobs, jobs+2, jobs+5];
            } else if (jobs <= 10) {
                jobsVariations = [Math.max(1, jobs-3), Math.max(1, jobs-1), jobs, jobs+3, jobs+7];
            } else if (jobs <= 20) {
                jobsVariations = [Math.max(1, jobs-5), Math.max(1, jobs-2), jobs, jobs+5, jobs+10];
            } else if (jobs <= 50) {
                jobsVariations = [Math.max(1, jobs-10), Math.max(1, jobs-5), jobs, jobs+10, jobs+20];
            } else {
                jobsVariations = [Math.max(1, jobs-20), Math.max(1, jobs-10), jobs, jobs+20, jobs+50];
            }
            
            // Supprimer les doublons et trier
            jobsVariations = [...new Set(jobsVariations)].sort((a, b) => a - b);
            
            // Limiter à 5 éléments max
            if (jobsVariations.length > 5) {
                jobsVariations = jobsVariations.slice(0, 5);
            }
            
            jobsVariations.forEach(jobCount => {
                const plan = selectPlan(jobCount);
                
                let planCost;
                if (plan.isPerJob) {
                    planCost = jobCount * plan.price; // Pay-per-use
                } else if (plan.price === null) {
                    planCost = Math.max(1500, jobCount * 150); // Grands comptes
                } else {
                    planCost = plan.price * 12; // Abonnement mensuel
                }
                
                let currentCost = 0;
                if (useCabinet) {
                    currentCost = jobCount * avgSalary * (commission / 100);
                } else {
                    currentCost = jobCount * jobboardCost + jobCount * timePerHire * hrRate;
                }
                
                const tenexCost = planCost + jobCount * (useCabinet ? 5 : timePerHire) * hrRate;
                const saving = currentCost - tenexCost;
                const percent = currentCost > 0 ? (saving / currentCost * 100).toFixed(1) : 0;
                
                const row = document.createElement('tr');
                if (jobCount === jobs) {
                    row.style.background = 'linear-gradient(90deg, rgba(102,126,234,0.2) 0%, rgba(118,75,162,0.2) 100%)';
                    row.style.fontWeight = 'bold';
                    row.style.border = '2px solid #667eea';
                }
                
                row.innerHTML = `
                    <td>${jobCount} ${jobCount === jobs ? '👈' : ''}</td>
                    <td>${plan.name}${plan.isPerJob ? ' (PPU)' : ''}</td>
                    <td>${currentCost.toLocaleString('fr-FR')} €</td>
                    <td>${tenexCost.toLocaleString('fr-FR')} €</td>
                    <td style="color: ${saving >= 0 ? '#10b981' : '#ef4444'}; font-weight: bold;">${saving.toLocaleString('fr-FR')} €</td>
                    <td style="color: ${saving >= 0 ? '#10b981' : '#ef4444'}; font-weight: bold;">${percent}%</td>
                `;
                
                tbody.appendChild(row);
            });
        }
    </script>
</body>
</html>
