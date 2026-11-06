# SAA Sprint — AWS Solutions Architect Associate (SAA-C03) in 5 days

A Duolingo-style study app for the **AWS Certified Solutions Architect – Associate (SAA-C03)** exam. Built for people with a full-time job and a few evenings to prepare.

The hard part of SAA-C03 isn't the services. It's that every option sounds right and two are nearly identical: SQS standard or FIFO, CloudFront or Global Accelerator, EFS or FSx, Multi-AZ or read replica, pilot light or warm standby. This app drills exactly those decisions.

**Live demo:** _add your Vercel URL here_

## What's in it

- **Scenario questions written to confuse you the way the real exam does**, with a reason for *every* option (why the right one is right and why each distractor is wrong)
- **Quick lessons** (5 questions, instant feedback) weighted toward your weakest domain
- **Timed mock exam** at 2 minutes per question, with a full review and per-domain score
- **Fix my misses**: every wrong answer goes on a list until you get it right
- **Service Lab**: 14 side-by-side tables of the pairs everyone mixes up, each with an "exam tell"
- **53 trigger keywords** ("exactly-once + order" → SQS FIFO, "static IP + UDP" → Global Accelerator) as tap-to-lock cards
- **60-second drill**: keyword in, service out
- **Streaks, XP, confetti**, and a readiness score weighted by the official domain split
- **5-day plan** ordered by exam weighting (Secure 30% → Resilient 26% → Performance 24% → Cost 20%) plus exam-day tactics
- Updated for 2026 service names (Amazon Data Firehose, SageMaker AI, Bedrock, DynamoDB Standard-IA)

Everything saves in your browser's local storage. No account, no ads, no tracking, nothing for sale.

## Run it

It's one static HTML file with no build step.

```bash
git clone https://github.com/<you>/saa-sprint.git
cd saa-sprint
open index.html        # or just double-click it
```

### Deploy to Vercel

1. Push this repo to GitHub.
2. Go to [vercel.com/new](https://vercel.com/new) and import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty.
4. Click **Deploy**.

Or from the terminal:

```bash
npm i -g vercel
vercel --prod
```

## Add or fix questions

All content lives at the top of the `<script>` in `index.html`:

| Array | What it holds |
|---|---|
| `QUESTIONS` | `{id, d, q, o, a, w, k}` — domain (`sec`/`res`/`perf`/`cost`), stem, 4 options, correct index, a reason per option, trigger keyword |
| `PAIRS` | Side-by-side comparison tables for the Lab |
| `TRIG` | `[keyword, service]` pairs for the trigger cards and drill |
| `PLAN` / `TACTICS` | The 5-day plan and exam tactics |

PRs with new questions are welcome. Every option needs a reason, and the wrong options should be plausible.

## Exam facts (SAA-C03)

| | |
|---|---|
| Questions | 65 (50 scored, 15 unscored) |
| Time | 130 minutes |
| Passing score | 720 / 1000 (scaled) |
| Domains | Secure 30% · Resilient 26% · High-performing 24% · Cost-optimized 20% |

Check the [official exam guide](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/solutions-architect-associate-03.html) before you book, in case AWS has updated the blueprint.

## Disclaimer

Not affiliated with or endorsed by Amazon Web Services. All questions are original and written against the public exam guide; this is **not** an exam dump. No study tool can guarantee a pass. Use it alongside hands-on practice and the official exam guide.

## License

MIT
