# Sl0ptiminer licence

Licence version 1. It applies to Sl0ptiminer 0.8.3 and to later releases supplied with this same text.

Sl0ptiminer is made and operated by **Evern00b**, an independent developer established in Finland. Contact for
licence matters, security, privacy and consumer claims: `security@sl0ptiminer.com`.

## 1. In short

- You may mine privately or commercially on machines you own or are authorised to operate.
- A compulsory developer fee uses a percentage of active mining time, at the rate set for the algorithm you mine
  (section 5). You pay nothing separately.
- The miner connects to your pools and checks for updates at the official site and GitHub. Sending a benchmark result or
  a fault report to us is a separate choice (section 6).
- Your mining can pause after 24 hours of healthy mining without a completed fee window. A fee-setting mismatch stops
  mining (section 5). The minimum-version rule can stop mining for you and for the developer after seven days, and so
  can 30 days without a verified update file (section 8).

## 2. Accepting this licence

Read and accept these terms before installing, running or distributing the package. By taking one of those steps, you
accept them. Every time the program starts mining, it first prints where this licence is and the developer fee rate
for the algorithm you mine; by starting mining you accept that fee. If you act for a company or another person, you
must be authorised to accept these terms for them. You can mine without submitting a benchmark result or a fault
report.

## 3. What you may do

Evern00b grants you a non-exclusive licence to run the published program on any number of machines you own or are
authorised to operate, for private or commercial mining. You may copy the unchanged package within your operation. You
may distribute or mirror the complete, unchanged package free of charge with its licence texts and signatures. A mirror
must identify itself as unofficial and link to the official site. It may use the program name to identify the package.
Each recipient receives a licence directly from Evern00b. This licence continues until it ends under section 14,
subject to the operating limits in sections 5 and 8. Transfer is permitted only where the law gives you that right.

## 4. What you may not do

You must not modify, repack or reverse engineer the program, run a modified copy, remove or change its notices or
signatures, deliberately defeat the developer fee, or knowingly help someone defeat it. You must not sell the program,
charge for access to the program itself, bundle it into another product, use it for hidden mining or in a botnet, run
it without the permission of the person responsible for the machine, or use it for any unlawful activity.

Sections 3 and 4 do not take away statutory rights to necessary copies, changes and backups, to study and test the
program during lawful use, to decompile it where needed to correct errors or, under the conditions set by law, to make
programs work together, or to resell it where the law permits.

## 5. The developer fee

- The fee is a percentage of active mining time, fixed for each algorithm in each release. The page "How the developer
  fee works" on the official site lists the rates, and the miner prints the rate for your algorithm before mining.
  The miner schedules fee windows roughly hourly during active mining; the first becomes due at a variable point in the
  first hour. During the same run, unpaid fee time carries forward, up to two fee windows, also across pool
  reconnects. The same rule applies on a test network.
- A fee window mines on the pool you are mining on at that time. Shortly before a window is due, the miner tries to
  open a second connection to that pool. It logs in there with the developer's address, followed by your worker name if
  you set one, and with the password field you set for that pool.
- While your mining devices are working on a developer job, their computing time and the electricity they use go
  towards the fee. That is what the fee costs you. The fee is shown live in the miner.
- The fee cannot be switched off. If the fee connection fails, the miner normally goes back to your jobs and tries
  again later. A fee window completes when the pool accepts the fee login, supplies a job and the connection stays up
  for the whole window. After 24 accumulated hours on your jobs, outside a fee window and while your pool has accepted
  one of your shares in the preceding 30 minutes, without a completed fee window, your mining pauses. The miner
  explains the pause and keeps your jobs paused while it retries the fee connection. A completed window ends the pause.
- If a check finds that the fee settings or the developer's login name differ from those for this release, the miner
  reports a mismatch, stops mining and directs you to reinstall the official package.
- A new release may have different rates. A minimum-version warning does not mean that you agree to a different fee.

## 6. Connections and data

1. Your active pool receives your IP address, wallet address, worker name, password field, shares and the miner
   version. While mining on a backup pool, the miner checks earlier pools by logging in with the wallet, worker name
   and password set for each; it sends no shares on these checks. Fee mining uses the
   developer's address, followed by your worker name if you set one, on your active pool (section 5).
2. When it checks for updates, the miner requests a signed version file from both the official site and our GitHub
   release repository. Hosts reached by those requests see your IP address. `--no-update-check` silences release news,
   including security news. The update-file downloads, the minimum-version warnings and the update-contact rule
   (section 8) continue.
3. Benchmark sharing is optional. A submitted result may appear individually in public. A share link contains its
   result: anyone who receives the link, including a mining service that receives your logs, can read it before you
   submit it to us. A command containing `--share-benchmarks` can upload eligible results automatically.
   `--no-share-benchmarks` stops uploads, questions and share links in the mining log; the miner can still save
   results locally.
4. A fault may create a local record. The miner sends us a fault report only if you request it by command or submit
   it from its report page. Your mining operating system may forward logs or status messages to its own service.

Benchmark results and fault reports go to `bench.sl0ptiminer.com`. The privacy notice on the official site
(`/privacy/`) says what is sent, who receives it, your choices and how long it is kept.

## 7. What the program does on your machine

- The miner stores your settings, tuning, minimum-version state, benchmark choices and latest results, and recent
  faults in your user configuration folder. It also caches compiled graphics programs. With `--state-file` it writes
  mining statistics to the file you name; the screen and `--line` modes can also write a log file (`--log-file`). A
  log may contain a readable share link (section 6, point 3).
- Before it starts mining, it verifies the program file and the files named in the signed release list, and does not
  mine if they do not match.
- None of our packages installs the program as a service or makes it start by itself. The Linux install command and
  the updater start and stop nothing. On a mining operating system, that system starts the miner, and starts it again
  after it stops, as your settings there say.
- The miner reads available hardware measurements. It does not change clocks, voltage, power limits or fans.
- It can mine with less to limit heat. On a Mac without a fan it starts on two processor threads, or on the count that
  stayed cool the last time, and uses fewer while macOS reports that the machine is getting hot, unless you set the
  thread count with `-t`. On Linux it can pause processor mining when the processor gets too hot. `--temp-limit` lowers
  the limit it uses, or sets one if the processor reports none. HiveOS and mmpOS default to a warning only, other Linux
  systems to a pause; `--on-overheat` or the menu changes that. A pause can end when the processor cools, or after five
  minutes without a temperature reading. The miner has no heat protection for graphics cards, which keep mining during a
  processor pause. These functions depend on the sensors your system offers, can be off or stop working, and are not a
  safety device: they do not replace your hardware's own protection or your supervision (section 9).

## 8. Updates and versions

- The miner does not install new versions automatically. By default it shows news of newer releases with security,
  network or fault fixes; below the minimum version it shows the minimum-version warning instead. On Linux, run the
  install command again; it keeps the previous version and removes older ones from its own folder. On HiveOS, change
  the version in your flight sheet. On a Mac and on other mining operating systems, get the new package from the
  official site.
- **Minimum supported version.** For a serious fault affecting security or the collection or calculation of the
  developer fee, we may publish a signed minimum version, and only for such a fault. The program applies it by version
  number on every platform. You can decline the update. A version below the minimum says so at once and reminds you
  daily. Seven days of elapsed time after this installation first detects that the running version is below the minimum,
  that version stops mining, for you and for the developer. A version that meets the minimum can mine again. A lower
  minimum in a later update file, or a failed download, leaves the current minimum in force. The miner tries to save the
  minimum and the time it first found the running version below it. On restart it uses the saved minimum and any saved
  date for that version. If no date is available, the seven days start when it next detects that version below the
  minimum. Running a version that meets the minimum clears the old warning dates. `--no-update-check` does not switch
  this check off. You keep the remedies that mandatory law gives you.
- **Update contact.** A verified update file is one whose release-key signature the miner accepts. If the miner
  receives no verified update file from the official site or our release repository for 30 days, it stops mining, for
  you and for the developer. It warns daily from seven days before. It applies this rule only after an update check in
  the current run has failed, so a machine that was off for a while mines until that check. A verified file ends a
  warning; after a stop, restore the update-file downloads from either source and start the miner again. The miner
  tries to save when it last received a verified update file. A failed save does not change the current run's clock.
  On restart it uses the last saved time, or the start of that run if no valid past time is available.
  `--no-update-check` does not switch this rule off.
- Only packages from the official site and our release repository are published by us. Check every package, wherever
  you got it, as the page "Security and verification" describes.
- A network upgrade can cause an older version's shares to be rejected. Individual user support is not available.
  Consumers keep any rights they have to notice and delivery of necessary updates.

## 9. What is in your hands

- Observe the mining and tax rules that apply to you, and your electricity, hosting and pool terms.
- **Before mining.** Mining places a sustained load on your equipment. Checks for your setup include the following.
  - Check that the circuit can carry the rig's sustained load together with other equipment on it. If its capacity is
    uncertain, ask the person responsible for the installation or a qualified electrician before mining.
  - Use power supplies, cables, plugs and connectors rated for the sustained load. Follow the equipment
    manufacturers' instructions and replace damaged components before use.
  - Use a stable case or frame suited to the equipment. Keep combustible materials clear of hot components and leave
    cooling paths open.
  - Have any changes to fixed wiring made by someone authorised for that work under local law.
  - Keep hardware thermal protections enabled. Supervise the rig, including after changing clock or power settings.
    Section 7 explains the limits of the miner's processor heat control. The miner provides no heat protection for
    graphics cards.
  - Stop mining if cooling fails, a connector overheats, a breaker trips repeatedly or you notice a burning smell.
    Have the cause corrected before mining again.
- Keep your wallet address and pool settings correct. The program cannot check that an address is yours.
- Your worker name is visible at your pool, and during a fee window it appears there after the developer's address. A
  pool that shows addresses in public may then list it, with your fee hashrate, beside other users' worker names on
  the developer's address page. Choose a worker name that says nothing about you.

## 10. Benchmark figures

The benchmark page distinguishes our measurements from unverified user reports. A result or an average does not
guarantee what your hardware will produce or earn.

## 11. No guarantee

We do not guarantee a particular hashrate, earnings, acceptance of shares by your pool or uninterrupted mining.

## 12. Liability

**12.1 Business use.** If you use Sl0ptiminer predominantly for business purposes, we are not liable for lost earnings,
lost or rejected shares or blocks, lost coins, electricity costs, loss of data, downtime, damage to or wear of
hardware, or indirect or consequential damage.

For claims arising in a 12-month period starting with the first claim, our total liability is the greater of EUR 50
and the euro value of the fee your use produced in the 12 months before that first claim. That value is estimated from
pool records and exchange rates reasonably available to either party, using the rate on the date of each credit.

**12.2 Consumers.** Section 12.1 does not apply to consumers. You keep your statutory remedies and rights to
compensation.

**12.3 Exceptions.** Nothing in this licence limits liability for death or personal injury, intentional harm, gross
negligence, liability under product liability law, or any other liability that the law does not allow us to limit.

## 13. Conformity

Where consumer law provides a legal guarantee of conformity for digital content, it applies to Sl0ptiminer. Send
defect claims to `security@sl0ptiminer.com`.

## 14. End of the licence

You may end your licence at any time by removing the program. We may end it immediately for deliberate fee tampering,
unauthorised mining or another serious breach that cannot reasonably be put right. For other breaches of the use or
distribution terms we may end it only if you fail to correct the breach within a reasonable time after we tell you
about it.
When your licence ends, stop using and distributing the program and remove the copies you control, subject to rights
and duties under law. Recipients who comply keep their licences. Sections 10 to 13 and 16 continue to apply after the
licence ends.

## 15. Other people's work, names

For third-party components you keep the rights their own licences give you: see `THIRD-PARTY-NOTICES.txt` in the package
or run `sloptiminer --licenses`. Sl0ptiminer and its logo belong to Evern00b. Other names belong to their owners.
Sl0ptiminer is independent of the projects it supports. Copyright (c) 2026 Evern00b. All other rights are reserved.

## 16. Law, disputes, general

- Finnish law governs this licence. Consumers keep the mandatory protection and the courts available to them under
  the law that applies to them.
- You may not use or export the program in breach of sanctions or export rules that apply to you.
- If a term is unenforceable, the remaining terms apply where the agreement can continue without it.
- The terms supplied with your installed version continue to apply to it. Read the terms of a different release before
  you install it.
- This English text is the original. Translations are for convenience.
