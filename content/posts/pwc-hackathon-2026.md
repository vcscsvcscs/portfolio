+++
draft = false
date = 2026-04-16T00:00:00+02:00
title = "PwC Hackathon 2026: Org Pondus and AI-Driven Organization Design"
summary = "My team and I took part in the PwC Hackathon 2026 with Org Pondus: an AI-agent and weighted-graph concept for data-driven hiring, workforce planning, retention, and organizational strategy."
tags = ["hackathon", "pwc", "ai", "agents", "aws", "bedrock", "agentcore", "knowledge-graph", "hr-tech"]
categories = ["hackathons"]
+++

## PwC Hackathon 2026
**April 16, 2026**  
**PwC Hungary, Budapest**  
Pre-screening round • business concept pitch • MVP canvas • ROI planning • hackathon delivery plan

My team and I took part in the **PwC Hackathon 2026**, a high-profile and unusually structured hackathon in Budapest. I joined with **Erdős Péter Zsombor** and **Vargha Bendegúz Attila**, my brother, under the team name **The Professionals**.

This event felt different from most hackathons I have attended. Before reaching the final build phase, teams first had to pass a pre-screening process and then prepare a serious pitch package: a **6-8 slide business concept**, an **MVP canvas**, an **ROI model**, and a realistic **hackathon execution plan**. We did not make it into the final 15 teams, but I still see the experience as valuable. We created a meaningful proposal, refined it under pressure, and made excellent professional connections along the way.

![The Professionals team at the PwC Hackathon 2026](/images/pwc-hackathon-2026-team.png)

One of the highlights for me was the chance to speak with senior PwC Hungary leadership, including the country leadership, and to have technical conversations with the heads of Cloud Engineering and AI Engineering. Those discussions made the event feel much more than a competition: it was also a rare opportunity to test an idea with people who understand both enterprise technology and business transformation.

## Our proposal: Org Pondus
Our concept was called **Org Pondus**: an AI-agent and weighted-graph based platform for developing and protecting organizations.

The core problem we wanted to address is that many organizations still make hiring, workforce planning, and internal capability decisions without a clear data-driven map of their own structure. Too often, these decisions are based on intuition, fragmented information, or subjective managerial impressions. In large companies, this can lead to the wrong person being hired for the wrong role, hidden capability gaps, overloaded key teams, underused departments, and slow organizational growth.

**Org Pondus** was designed to create a more objective, continuously updated view of an organization by combining:
- Existing company knowledge bases and internal documentation
- HR and ticketing system events
- Public and market data where relevant
- A weighted organizational graph
- Specialized AI agents for hiring, workforce planning, and strategy evaluation

The goal was not to replace leadership judgment. It was to give leaders, HR teams, and managers a better factual base for decisions: where capacity is missing, which teams are overloaded, which capabilities are strategically important, and when the organization should hire, rebalance, or invest in retention.

## Technical direction
The technical proposal was an agent-based architecture running in a cloud environment, with AWS as the reference implementation.

![Org Pondus agent system](/images/pwc-hackathon-2026-agent-system.png)

At the center of the design was **Amazon Bedrock AgentCore Runtime**, coordinating multiple specialized agents:
- **Hiring Manager Agent** for role definition and hiring recommendations
- **Organization Tree Balancing Agent** for capacity and structure analysis
- **Organization Strategy Evaluator Agent** for strategic trade-off assessment
- **Workforce Decisionmaker Agents** for operational decision support

These agents would connect through **AgentCore Gateways** to enterprise systems and knowledge sources such as ticketing tools, LinkedIn, Hays, internal knowledge bases, and organization data. A **Bedrock Knowledge Base** and an **Amazon Neptune** graph layer would provide the system with both semantic knowledge and structured organizational relationships.

![High-level Org Pondus architecture](/images/pwc-hackathon-2026-high-level-architecture.png)

The proposed high-level architecture included:
- **Route 53, CloudFront, S3, API Gateway, WAF, and Lambda** for a serverless web and API layer
- **EventBridge** for processing incoming HR and ticketing events in near real time
- **Bedrock AI models** for reasoning, recommendation generation, and natural-language interaction
- **Bedrock AgentCore Runtime** for orchestrating the agent system
- **Bedrock Knowledge Base** for company-specific knowledge retrieval
- **Amazon Neptune** for the weighted organizational graph
- **MCP-style integrations** for connecting to tools such as Jira, Hays, LinkedIn, and internal systems

We also planned a frontend that would visualize the organizational graph, surface critical weaknesses and strengths, and allow strategic priorities to be configured so the recommendations could be aligned with company goals.

## Business value and ROI
The business case focused on measurable improvements in hiring, retention, and organizational planning.

We proposed a SaaS and usage-based pricing model, starting with data-rich technology companies and later expanding toward SMEs and enterprise clients. The pitch estimated an initial implementation investment of about **15,000 EUR** for a production-usable first iteration, followed by monthly operating costs depending on infrastructure, model usage, support, and sales effort.

The expected customer value included:
- Faster and cheaper hiring workflows
- Lower employee turnover through earlier risk detection
- Better-balanced workload distribution
- More objective capacity planning
- Clearer visibility into organizational strengths and weaknesses
- Continuous reporting, prediction, and decision support based on real data

The idea was ambitious, but intentionally grounded: start with an MVP, validate with alpha-test companies, and then deepen integrations as the organizational model becomes more useful.

## What I took away
Even though we did not advance to the final 15, I am proud of what we built as a concept. The format forced us to think beyond a demo and consider feasibility, ROI, implementation planning, and enterprise adoption from the beginning.

I am grateful to **PwC** for organizing the event and creating a space where technical and business thinking could meet. I am also thankful to **Erdős Péter Zsombor** and **Vargha Bendegúz Attila** for the teamwork, energy, and honest discussions that shaped the proposal.

This was a strong reminder that a hackathon can still be successful even without a final-stage placement, if it produces a better idea, sharper thinking, and meaningful professional relationships.
