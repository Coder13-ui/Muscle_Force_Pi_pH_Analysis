# Muscle_Force_Pi_pH_Analysis
% MATLAB Code Template for Analyzing Muscle Force vs. Pi and pH Levels

% Description:
% This script analyzes the effect of inorganic phosphate (Pi) concentrations 
% and pH levels on muscle force at various calcium ion concentrations (pCa levels).

% Define Pi concentrations in mM
pi_concentrations = [];  % Fill in with your data

% Define force data at pH 7.4
force_neutral = [];  % Fill in with your data

% Define force data at pH 6.5
force_acidic = [];  % Fill in with your data

% Define force data at various pCa levels (for neutral pH)
force_pCa58_neutral = [];  % Fill in with your data
force_pCa59_neutral = [];  % Fill in with your data
force_pCa60_neutral = [];  % Fill in with your data

% Define force data at various pCa levels (for acidic pH)
force_pCa58_acidic = [];  % Fill in with your data
force_pCa59_acidic = [];  % Fill in with your data
force_pCa60_acidic = [];  % Fill in with your data

% Create the plots
figure;

% Plot for neutral pH
subplot(2, 2, 1);
plot(pi_concentrations, force_neutral, 'o-', 'LineWidth', 1.5);
title('Force vs Pi at pH 7.4');
xlabel('Pi concentration (mM)');
ylabel('Force (% of max force)');
ylim([0 110]);
grid on;

subplot(2, 2, 2);
hold on;
plot(pi_concentrations, force_pCa58_neutral, 'o-', 'LineWidth', 1.5, 'DisplayName', 'pCa 5.8');
plot(pi_concentrations, force_pCa59_neutral, 's--', 'LineWidth', 1.5, 'DisplayName', 'pCa 5.9');
plot(pi_concentrations, force_pCa60_neutral, '^:', 'LineWidth', 1.5, 'DisplayName', 'pCa 6.0');
title('Force vs Pi at various pCa (pH 7.4)');
xlabel('Pi concentration (mM)');
ylabel('Force (% of max force)');
ylim([0 110]);
legend;
grid on;
hold off;

% Plot for acidic pH
subplot(2, 2, 3);
plot(pi_concentrations, force_acidic, 'o-', 'LineWidth', 1.5);
title('Force vs Pi at pH 6.5');
xlabel('Pi concentration (mM)');
ylabel('Force (% of max force)');
ylim([0 110]);
grid on;

subplot(2, 2, 4);
hold on;
plot(pi_concentrations, force_pCa58_acidic, 'o-', 'LineWidth', 1.5, 'DisplayName', 'pCa 5.8');
plot(pi_concentrations, force_pCa59_acidic, 's--', 'LineWidth', 1.5, 'DisplayName', 'pCa 5.9');
plot(pi_concentrations, force_pCa60_acidic, '^:', 'LineWidth', 1.5, 'DisplayName', 'pCa 6.0');
title('Force vs Pi at various pCa (pH 6.5)');
xlabel('Pi concentration (mM)');
ylabel('Force (% of max force)');
ylim([0 110]);
legend;
grid on;
hold off;

% Adjusting the layout
sgtitle('Effect of Pi on Muscle Force at Different pH Levels');

% Save the figure
saveas(gcf, 'Muscle_Force_vs_Pi_and_pH.png');
