# Deep Decision Analysis

Use this reference only after deep-mode routing. Apply the parts that affect the decision; do not force every section into the response.

## 1. Decision brief

Capture a compact brief:

| Field | Meaning |
|---|---|
| Decision | One actionable choice, not a broad topic |
| Deadline | Latest useful decision time |
| Horizon | Period over which outcomes and costs matter |
| Objectives | Outcomes the user values, with conflicts visible |
| Constraints | Hard limits that options must satisfy |
| Options | Proposed option, status quo, best feasible alternative, and delay or experiment when realistic |
| Stakeholders | Who acts, benefits, pays, can block, or responds |
| Reversibility | What can be undone, at what cost, and within what window |

Do not optimize before objectives and constraints are clear. Do not manufacture extra alternatives that are infeasible for this user.

## 2. Importance and uncertainty routing

Evaluate importance through impact breadth, impact depth, duration, and multiplier effects. Evaluate uncertainty through forecast difficulty, control, dependencies, and change speed.

| | Lower uncertainty | Higher uncertainty |
|---|---|---|
| Lower importance | Standardize, delegate, or decide quickly | Observe cheaply; avoid expensive analysis |
| Higher importance | Verify assumptions and execute in time | Run scenarios, gather discriminating evidence, preserve options, and install buffers and triggers |

Use judgment rather than an arbitrary summed score. A single catastrophic or irreversible dimension can justify deep analysis.

## 3. Information architecture

Classify information by function:

- **Foundational patterns:** reference classes, base rates, slow variables, mechanisms, and durable constraints. Use these to form priors, then test whether structural change weakens them.
- **Analytical insight:** models and interpretations that connect observations to hypotheses. Record alternative explanations and causal assumptions.
- **Current signals:** recent events, measurements, anomalies, and triggers. Treat these as noisy updates rather than automatic overrides.

For each material item, track:

| Field | Question |
|---|---|
| Claim | What exactly is asserted? |
| Source and date | Where and when did it originate? |
| Scope | To which population, place, or period does it apply? |
| Reliability | How credible are measurement and reporting? |
| Independence | Does it share a source or cause with other evidence? |
| Discrimination | Is it more expected under one hypothesis than another? |
| System link | Which variable or relationship does it inform? |
| Update effect | What belief or action should change? |
| Invalidation | What would make it obsolete or misleading? |

## 4. Bayesian reasoning

State competing hypotheses before updating. Begin with a relevant base rate or explain why none is defensible.

When numeric inputs are credible:

```text
prior odds = p / (1 - p)
likelihood ratio = P(E | H) / P(E | not-H)
posterior odds = prior odds × likelihood ratio
posterior probability = posterior odds / (1 + posterior odds)
```

Before multiplying likelihood ratios, group evidence by common source or causal origin. Adjust or avoid multiplication when independence is doubtful. Show assumptions and use ranges when inputs are ranges.

For nonnumeric evidence, use an ordinal direction and strength. Explain the counterfactual question: “How surprising would this evidence be if the competing hypothesis were true?”

Test each new item through five gates:

1. **Authenticity:** Is the observation trustworthy?
2. **Contrast:** Does it discriminate among hypotheses?
3. **Increment:** Is it new rather than duplicated?
4. **Robustness:** Does it survive sample, definition, timing, and source checks?
5. **Decision relevance:** Could it change belief, action, or the information plan?

## 5. System model

Map only the variables needed to expose non-obvious consequences. For each important relationship, note direction, sign, delay, confidence, and an alternative explanation.

Look for:

- reinforcing and balancing feedback loops;
- delayed costs or benefits;
- thresholds, bottlenecks, and nonlinear effects;
- shared causes that make evidence or risks correlated;
- stakeholder adaptation and competitive response;
- an action changing the environment from which its evidence was drawn;
- local optimization that worsens the whole system.

Treat every arrow as a causal hypothesis to be tested, not as established truth. Use scenarios when the model is too uncertain for point prediction.

## 6. Alternatives, costs, and scenarios

Compare each feasible option against the same horizon and objectives. Opportunity cost is the value of the best feasible alternative forgone.

Build three cost layers:

1. **Direct:** capital, operating expense, foregone income, time, financing, switching, and exit costs.
2. **Hidden:** career progression, skills, network, platform credibility, family life, health, attention, reputation, and path dependence.
3. **Uncertainty:** internal capacity risks and external policy, demand, technology, competition, or dependency changes.

Separate costs already included in an outcome estimate to prevent double-counting. Apply time discounting only when timing materially changes comparability.

Use best, base, and worst reasonable scenarios. A worst reasonable scenario must have a plausible causal path; it is not an imaginary maximum disaster. When probabilities are defensible:

```text
expected value(option) = Σ probability(scenario) × value(option, scenario)
relative expected value = expected value(option) - expected value(best feasible alternative)
```

Expected value is an input, not the decision rule. Apply constraints, risk concentration, reversibility, and user utility afterward.

## 7. Capacity and option value

Test downside against:

- financial reserves and obligations;
- time runway and deadline pressure;
- family and relationship capacity;
- psychological load;
- professional, legal, and reputational exposure;
- recovery route and recovery time.

Reject or redesign options with plausible ruin, irreversible harm, or no credible recovery path. Do not infer attractiveness merely because the loss is survivable.

Improve option value through a smaller pilot, staged funding, conditional commitment, diversification, a checkpoint, an exit clause, or a reversible first move. Define in advance:

- the maximum initial commitment;
- evidence required to expand;
- stop or exit conditions;
- the next review time;
- what remains protected if the attempt fails.

## 8. Recommendation and confidence

Recommend an option only relative to stated objectives and alternatives. Use conditional language:

> Prefer A over B if assumptions X and Y hold, because evidence Z outweighs the opportunity cost. Switch to B if trigger T occurs.

Assign confidence qualitatively:

- **High:** multiple reliable, discriminating, substantially independent evidence sources; stable mechanisms; limited model uncertainty.
- **Medium:** a reasonable leading case with material assumptions or correlated evidence.
- **Low:** weak base rates, poor discrimination, structural change, severe model uncertainty, or unresolved value conflict.

Confidence describes support for the recommendation, not certainty about the future.

## 9. Deep-mode output

Use the smallest subset that preserves decision quality:

1. Decision and alternatives
2. Objectives, constraints, and time horizon
3. Importance–uncertainty assessment
4. Evidence ledger and Bayesian update
5. System effects and second-order consequences
6. Scenario and opportunity-cost comparison
7. Capacity and recovery assessment
8. Conditional recommendation and confidence
9. Reversible action plan, cap, triggers, and review date
10. Unknowns that could reverse the conclusion

End with a decision-ready next step. Do not bury the recommendation under the framework.
