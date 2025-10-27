# linkedin
import { motion } from "framer-motion";
import { Github, Linkedin, Mail, Phone, MapPin, ExternalLink } from "lucide-react";

// Simple, clean, single‑page profile similar to the reference you shared.
// Pure React + Tailwind (no UI libraries). Drop into a Vite React project, or export via CRA.

const INFO = {
  name: "Gopi Chand",
  title: "Sr. AWS DevOps Engineer",
  about:
    "8+ years designing AWS platforms, automating CI/CD, and codifying infrastructure with Terraform and Kubernetes. I help teams ship faster, safer, and more reliably.",
  location: "New Jersey, IN (Open to Remote)",
  email: "gopisrinivas56@gmail.com",
  phone: "+1 8565179669",
  github: "https://github.com/your-github",
  linkedin: "https://www.linkedin.com/in/your-linkedin/",
};

const SKILLS = [
  { group: "Cloud & Infra", items: ["AWS", "VPC/TGW", "EC2", "RDS", "ElastiCache", "IAM", "S3", "CloudFront", "Route53"] },
  { group: "Containers & Orchestration", items: ["Docker", "Kubernetes (EKS)", "Helm", "ArgoCD"] },
  { group: "CI/CD & IaC", items: ["Jenkins", "GitHub Actions", "Terraform", "Ansible", "Packer"] },
  { group: "Observability & Security", items: ["Prometheus", "Grafana", "Datadog", "AppDynamics", "OWASP", "Vault"] },
  { group: "Languages", items: ["Python", "Bash", "Groovy"] },
];

const EXPERIENCE = [
  {
    company: "Citibank (via Vendor)",
    role: "Sr. AWS DevOps Engineer",
    period: "2022 – Present",
    bullets: [
      "Built EKS platform with GitOps (ArgoCD), IRSA, Helm standards, and autoscaling.",
      "Implemented reusable CI/CD templates (Jenkins/GitHub Actions) with OIDC to AWS.",
      "Hardened workloads with OPA/Gatekeeper, secrets encryption, and network policies.",
    ],
  },
  {
    company: "Gspann Technologies",
    role: "DevOps Engineer",
    period: "2019 – 2022",
    bullets: [
      "Migrated on‑prem to AWS using blue/green & canary; codified infra with Terraform.",
      "Created golden AMIs with Packer; standardized VPC, ALB, RDS modules.",
      "Rolled out Datadog/AppDynamics with service‑level dashboards & SLOs.",
    ],
  },
  {
    company: "Triculin Technologies",
    role: "Site Reliability Engineer",
    period: "2017 – 2019",
    bullets: [
      "On‑call SRE for mission‑critical apps; reduced MTTR by 45% via automation.",
      "Centralized logging with OpenSearch/ELK; actionable alerts with runbooks.",
    ],
  },
];

const PROJECTS = [
  {
    title: "AWS Landing Zone & Governance",
    link: "#",
    details:
      "Multi‑account setup with AWS Organizations, SCPs, SSO, central logging, and account vending; improved security posture and provisioning speed.",
    stack: ["Organizations", "SCPs", "IAM Identity Center", "CloudTrail", "Config"],
  },
  {
    title: "EKS Platform with GitOps",
    link: "#",
    details:
      "Terraform‑provisioned EKS, ArgoCD‑managed apps, Helm standards, IRSA, autoscaling, and ALB Ingress; reduced lead time by ~70%.",
    stack: ["Terraform", "EKS", "ArgoCD", "Helm", "ALB", "Karpenter/CA"],
  },
  {
    title: "CI/CD Modernization",
    link: "#",
    details:
      "Migrated from legacy Jenkins to GitHub Actions with reusable workflows, OIDC to AWS, and policy gates; improved change failure rate and MTTR.",
    stack: ["GitHub Actions", "Jenkins", "SonarQube", "Terraform Cloud"],
  },
];

const CERTS = [
  "AWS Certified DevOps Engineer – Professional",
  "AWS Certified Solutions Architect – Associate",
  "CKA (if applicable)",
];

function Chip({ children }) {
  return (
    <span className="text-xs md:text-sm inline-flex items-center px-2.5 py-1 rounded-full border bg-white/60 dark:bg-white/5">
      {children}
    </span>
  );
}

function SectionTitle({ children }) {
  return (
    <h2 className="text-xl md:text-2xl font-semibold tracking-tight mb-4">{children}</h2>
  );
}

export default function Profile() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-slate-50 to-white dark:from-slate-950 dark:to-slate-950 text-slate-900 dark:text-slate-100">
      {/* Header */}
      <header className="border-b sticky top-0 z-40 backdrop-blur bg-white/70 dark:bg-slate-950/60">
        <div className="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between">
          <a href="#home" className="font-bold tracking-tight">{INFO.name}</a>
          <nav className="hidden md:flex gap-6 text-sm">
            <a href="#about" className="hover:opacity-80">About</a>
            <a href="#skills" className="hover:opacity-80">Skills</a>
            <a href="#experience" className="hover:opacity-80">Experience</a>
            <a href="#projects" className="hover:opacity-80">Projects</a>
            <a href="#contact" className="hover:opacity-80">Contact</a>
          </nav>
        </div>
      </header>

      {/* Hero */}
      <main id="home" className="max-w-5xl mx-auto px-4">
        <section className="py-10 md:py-14">
          <div className="grid md:grid-cols-[220px_1fr] gap-6 items-center">
            <motion.div initial={{opacity:0, y:10}} animate={{opacity:1, y:0}} transition={{duration:0.4}} className="flex md:block justify-center">
              <div className="relative">
                <img
                  src="https://avatars.githubusercontent.com/u/00000000?v=4"
                  alt="Profile"
                  className="w-40 h-40 md:w-52 md:h-52 rounded-full object-cover border shadow-sm"
                />
                <span className="absolute -bottom-2 -right-2 bg-emerald-500 text-white text-xs px-2 py-0.5 rounded-full border">Open to work</span>
              </div>
            </motion.div>
            <motion.div initial={{opacity:0, y:10}} animate={{opacity:1, y:0}} transition={{duration:0.5}}>
              <h1 className="text-3xl md:text-4xl font-extrabold tracking-tight">{INFO.name}</h1>
              <p className="mt-1 text-lg md:text-xl text-slate-600 dark:text-slate-300">{INFO.title}</p>
              <p className="mt-3 text-slate-700/90 dark:text-slate-300/90 leading-relaxed">{INFO.about}</p>
              <div className="mt-4 flex flex-wrap gap-3">
                <a href={INFO.github} target="_blank" rel="noreferrer" className="inline-flex items-center gap-2 px-3 py-1.5 rounded-md border hover:bg-slate-50 dark:hover:bg-white/5"><Github className="w-4 h-4"/>GitHub</a>
                <a href={INFO.linkedin} target="_blank" rel="noreferrer" className="inline-flex items-center gap-2 px-3 py-1.5 rounded-md border hover:bg-slate-50 dark:hover:bg-white/5"><Linkedin className="w-4 h-4"/>LinkedIn</a>
                <a href={`mailto:${INFO.email}`} className="inline-flex items-center gap-2 px-3 py-1.5 rounded-md border hover:bg-slate-50 dark:hover:bg-white/5"><Mail className="w-4 h-4"/>Email</a>
              </div>
              <div className="mt-3 flex flex-wrap gap-3 text-sm text-slate-600 dark:text-slate-300">
                <span className="inline-flex items-center gap-1"><MapPin className="w-4 h-4"/>{INFO.location}</span>
                <span className="inline-flex items-center gap-1"><Phone className="w-4 h-4"/>{INFO.phone}</span>
              </div>
            </motion.div>
          </div>
        </section>

        {/* About */}
        <section id="about" className="py-6">
          <SectionTitle>About</SectionTitle>
          <div className="grid md:grid-cols-3 gap-4">
            <div className="md:col-span-2 space-y-2 text-slate-700 dark:text-slate-300">
              <p>I specialize in cloud foundations, platform engineering, and developer productivity. My approach: automate everything, enable paved roads, and build reliable systems with strong guardrails.</p>
              <p>Comfortable across networking, security, build systems, and observability — partnering closely with dev teams to deliver business outcomes.</p>
            </div>
            <div className="md:col-span-1 bg-white/60 dark:bg-white/5 border rounded-xl p-4">
              <p className="font-medium mb-2">Quick Highlights</p>
              <ul className="list-disc pl-5 text-sm space-y-1 text-slate-700 dark:text-slate-300">
                <li>70% faster releases with GitOps</li>
                <li>45% MTTR reduction via automation</li>
                <li>Org‑level guardrails with SCPs</li>
              </ul>
            </div>
          </div>
        </section>

        {/* Skills */}
        <section id="skills" className="py-6">
          <SectionTitle>Skills</SectionTitle>
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
            {SKILLS.map((s) => (
              <div key={s.group} className="border rounded-xl p-4 bg-white/60 dark:bg-white/5">
                <p className="font-medium mb-2">{s.group}</p>
                <div className="flex flex-wrap gap-2">
                  {s.items.map((i) => (
                    <Chip key={i}>{i}</Chip>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* Experience */}
        <section id="experience" className="py-6">
          <SectionTitle>Experience</SectionTitle>
          <div className="space-y-4">
            {EXPERIENCE.map((e) => (
              <div key={e.company} className="border rounded-xl p-4 bg-white/60 dark:bg-white/5">
                <div className="flex flex-col md:flex-row md:items-center md:justify-between gap-1">
                  <p className="font-semibold">{e.role} · {e.company}</p>
                  <p className="text-sm text-slate-500 dark:text-slate-400">{e.period}</p>
                </div>
                <ul className="mt-2 list-disc pl-5 space-y-1 text-sm text-slate-700 dark:text-slate-300">
                  {e.bullets.map((b, i) => (
                    <li key={i}>{b}</li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        </section>

        {/* Projects */}
        <section id="projects" className="py-6">
          <SectionTitle>Projects</SectionTitle>
          <div className="grid md:grid-cols-2 gap-4">
            {PROJECTS.map((p) => (
              <div key={p.title} className="border rounded-xl p-4 bg-white/60 dark:bg-white/5">
                <div className="flex items-center justify-between gap-2">
                  <p className="font-semibold">{p.title}</p>
                  {p.link !== "#" && (
                    <a href={p.link} target="_blank" rel="noreferrer" className="text-sm inline-flex items-center gap-1 hover:underline">
                      Case Study <ExternalLink className="w-4 h-4" />
                    </a>
                  )}
                </div>
                <p className="mt-2 text-sm text-slate-700 dark:text-slate-300">{p.details}</p>
                <div className="mt-3 flex flex-wrap gap-2">
                  {p.stack.map((s) => (
                    <Chip key={s}>{s}</Chip>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* Certifications */}
        <section className="py-6">
          <SectionTitle>Certifications</SectionTitle>
          <div className="flex flex-wrap gap-2">
            {CERTS.map((c) => (
              <Chip key={c}>{c}</Chip>
            ))}
          </div>
        </section>

        {/* Contact */}
        <section id="contact" className="py-8">
          <SectionTitle>Contact</SectionTitle>
          <div className="grid md:grid-cols-3 gap-4">
            <div className="md:col-span-2 border rounded-xl p-4 bg-white/60 dark:bg-white/5">
              <p className="text-slate-700 dark:text-slate-300">I’m open to Sr. DevOps / Platform / SRE roles and short‑term consulting engagements.</p>
              <div className="mt-3 flex flex-wrap gap-3">
                <a href={`mailto:${INFO.email}`} className="inline-flex items-center gap-2 px-3 py-1.5 rounded-md border hover:bg-slate-50 dark:hover:bg-white/5"><Mail className="w-4 h-4"/>Email</a>
                <a href={INFO.github} target="_blank" rel="noreferrer" className="inline-flex items-center gap-2 px-3 py-1.5 rounded-md border hover:bg-slate-50 dark:hover:bg-white/5"><Github className="w-4 h-4"/>GitHub</a>
                <a href={INFO.linkedin} target="_blank" rel="noreferrer" className="inline-flex items-center gap-2 px-3 py-1.5 rounded-md border hover:bg-slate-50 dark:hover:bg-white/5"><Linkedin className="w-4 h-4"/>LinkedIn</a>
              </div>
            </div>
            <div className="border rounded-xl p-4 bg-white/60 dark:bg-white/5">
              <p className="font-medium mb-2">Availability</p>
              <ul className="list-disc pl-5 text-sm space-y-1 text-slate-700 dark:text-slate-300">
                <li>Notice: 2 weeks</li>
                <li>Timezone: IST / flexible</li>
                <li>Remote / Hybrid</li>
              </ul>
            </div>
          </div>
        </section>

        <footer className="py-10 text-center text-xs text-slate-500">© {new Date().getFullYear()} {INFO.name}. All rights reserved.</footer>
      </main>
    </div>
  );
}
