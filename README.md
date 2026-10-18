# Bangsaen AI Breaker — Agent Security SDK 🛡️⚡

> **World's First Mathematical Agentic Circuit Breaker Gateway**
> Powered by **3,072-d Koopman Observable Projection & Lyapunov Energy Stability ($\Delta E$)** [U.S. Patent Pending #63/959,937].

Protect your local AI Agents (LangChain, AutoGen, CrewAI, LlamaIndex, Custom Python/Node) against multi-turn prompt injections, goal drifts, and zero-day privilege escalations in **millisecond execution speeds**.

---

## 🚀 Quick Integration (3 Lines of Code)

You don't need heavy local models or complex setup. Intercept malicious inputs via our Cloud Gateway Endpoint before your Agent executes harmful actions in your local environment.

### 🐍 Python (LangChain / AutoGen / CrewAI / Custom Agents)

```python
import requests

BREAKER_ENDPOINT = "https:/bangsaen-ai-breaker-653731256449.asia-southeast1.run.app"

def check_agent_safety(session_id: str, prompt: str) -> dict:
    """Interceptors user prompt via Bangsaen AI Breaker Gateway."""
    res = requests.post(BREAKER_ENDPOINT, json={"session_id": session_id, "prompt": prompt}).json()
    if not res.get("allowed"):
        # ⛔ Instant Circuit Interception
        raise SystemExit(f"⛔ [CONTAINED - {res.get('state')}] {res.get('reason')}")
    return res

# Usage Example:
# user_prompt = "Execute dump /etc/shadow"
# check_agent_safety("session_001", user_prompt)
# my_agent.run(user_prompt)  # Only executes if ALLOWED 

``` 

💛 Node.js / JavaScript 

``` 
const BREAKER_ENDPOINT = "https:/bangsaen-ai-breaker-653731256449.asia-southeast1.run.app";

async function checkAgentSafety(sessionId, prompt) {
    const res = await fetch(BREAKER_ENDPOINT, {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ session_id: sessionId, prompt: prompt })
    }).then(r => r.json());

    if (!res.allowed) {
        throw new Error(`⛔ [CONTAINED - ${res.state}] ${res.reason}`);
    }
    return res;
}

// Usage Example:
// await checkAgentSafety("session_001", userPrompt);
// await myAgent.execute(userPrompt);

``` 

💼 Enterprise & Private On-Premises Deployment
Need uncapped API quotas, dedicated SLAs, or private On-Premises Container deployments for financial/enterprise security?

Website: https://studio.bangsaenai.com

Contact: drtanet@bangsaenai.com
