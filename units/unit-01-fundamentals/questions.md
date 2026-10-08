# Unit 1 — Review Questions (English)

Interview-style questions and answers for every concept covered so far.
Read the question out loud, answer it out loud in English, then check.

---

## 1. What is Software Testing?

**Q: What is software testing, and what does it deliver to the team?**

**A:** Software testing is the activity of evaluating a system or a component to find out whether it works as expected, and to provide information about its quality and its risks. It does not deliver a verdict of "no bugs". It delivers information: what works, what does not, under which conditions, and what was covered.

**Q: Why is the report "I didn't find any bugs" dangerous?**

**A:** Because it can be read as "the product has no bugs". Testing can show the presence of defects, not their absence. A good report says what was covered, under which conditions, and what the evidence is. The absence of evidence is not evidence of absence.

**Q: What is the difference between an `expected result` and an `actual result`?**

**A:** The `expected result` is the behavior defined by the requirements or the design — what the system should do. The `actual result` is what I observe when I execute the test. A `failure` is the gap between the two.

---

## 2. QA vs QC

**Q: What is the difference between QA and QC?**

**A:** QA (Quality Assurance) is process-oriented and preventive: it improves the way the team works so that defects are not created. QC (Quality Control) is product-oriented and detective: it checks the already-built product to find defects. QA prevents defects; QC finds defects.

**Q: Give one concrete QA activity and one concrete QC activity.**

**A:** QA: writing clear user stories, doing code reviews, defining coding standards. QC: executing test cases, inspecting a build, verifying the delivery against the acceptance criteria.

**Q: A defect reached production. Is that a QA failure or a QC failure?**

**A:** Both, usually. QC did not catch it, but the deeper question is why the process allowed it to be created and shipped — that is the QA side.

---

## 3. Verification vs Validation

**Q: What is the difference between verification and validation?**

**A:** Verification checks that the product complies with what is specified: "Are we building the product right?". Validation checks that the product fulfills the real need of the user in their real context: "Are we building the right product?".

**Q: I executed the app and found a bug. Does that make it verification or validation?**

**A:** Neither. The activity does not decide. What decides is where the expectation came from. If the rule was written by a person in a document — a user story, a requirement, a manual — it is verification. If the rule comes from how the user actually works, even if nobody ever wrote it, it is validation.

**Q: What happens if there is no `test basis`?**

**A:** Verification is impossible: there is nothing to compare against. But the answer is not "I can't test". It is to validate, and to report the gap and propose the missing `acceptance criteria`.

**Q: Can a product pass verification and fail validation?**

**A:** Yes, and that is the whole point of the distinction. The product can match the specification perfectly and still not solve the user's real problem. That is a requirement defect, not a code defect.

---

## 4. Error / Defect / Failure

**Q: What is the difference between an `error`, a `defect` and a `failure`?**

**A:** An `error` is a human action that produces an incorrect result. A `defect` is an imperfection left in an artifact — requirements, design, code, data, configuration — and it is the consequence of the error. A `failure` is the observable manifestation of the defect when the software is executed.

**Q: How do you decide which one you are looking at?**

**A:** I ask who the sentence is about. If it is about a person doing something, it is an `error`. If it is about an artifact being the way it is, it is a `defect`. If it is about the app running, it is a `failure`.

**Q: Can a defect exist without ever producing a failure?**

**A:** Yes. Dead code, unreachable branches, or conditions that never happen. The defect is there, latent. Not seeing it does not mean it is not there.

**Q: A user reports that "the system is broken" because he cannot lend an item that is already lent to someone else. Is that a defect?**

**A:** No. The system is behaving exactly as expected, so there is no `failure` and no `defect`. It is a wrong expectation from the user. Discarding reports that are not bugs is one of the most valuable skills of a tester.

**Q: How do you write a `failure`?**

**A:** With three parts: what I do (the steps), what I expected (`expected result`) and what happened (`actual result`). Without the `expected result` there is no failure — there is an opinion.

---

## 5. Root Cause

**Q: What is a `root cause`?**

**A:** The deepest cause that, if corrected, removes the problem **and its siblings** — not just the visible symptom.

**Q: How do you know you reached the root cause and not just another layer?**

**A:** With two tests. First: does it explain why the same kind of problem appeared in more than one place? Second: is it a missing or weak step in the way the team works, instead of a one-time act by a person? If my answer is a person, I have not arrived yet.

**Q: What is the difference between an `error` and a `root cause`?**

**A:** An `error` is a one-time human act. A `root cause` is why that error was possible — usually a missing or weak step in the process, so it does not depend on who does the work.

**Q: Give an example of a root cause.**

**A:** Three different bugs appeared: a deleted category's name stayed taken, a deleted instructor's email stayed taken, and a deleted site's name stayed taken. Three different fixes, one single root cause: the team has no mandatory step where uniqueness and lifecycle rules are defined before coding.

**Q: What is the difference between a `symptom` and a `root cause`?**

**A:** The `symptom` is what you see — the `failure`. The `root cause` is why it was possible in the first place. Fixing the symptom makes the bug disappear for a while; fixing the root cause stops the family of bugs from being born.

**Q: Is the root cause always a fact?**

**A:** No. It is a hypothesis, and it has to be validated: if I correct this, do the symptoms stop appearing? If they don't, the hypothesis is wrong.

---

## 6. Testing vs Debugging

**Q: What is the difference between testing and debugging?**

**A:** Testing finds failures and gives information about quality and risk — it does not fix anything. Debugging locates, analyzes and corrects the cause of a failure in the code. Testing finds; debugging fixes.

**Q: Who does each one?**

**A:** Testing is done by the tester / QC. Debugging is usually done by the developer — but it depends on where the defect lives: if it is in the requirement, the PO fixes it; if it is in the data, the data is fixed; if it is in the code, the developer fixes it.

**Q: What comes after the developer says "it's fixed"?**

**A:** Retesting: running that same test case again to confirm the failure no longer happens. "It's fixed" is not evidence — the evidence is the retesting.

**Q: Is debugging the same as testing while looking at the code?**

**A:** No. Debugging starts after something failed. Testing is what finds it in the first place. The border is not the hat you wear — it is the objective.

**Q: Why shouldn't the same person fix the bug and validate the fix?**

**A:** Because then nobody controls anybody: the fix certifies itself. It is the same problem as an inspector who also does the repairs.

**Q: Does retesting confirm that everything still works?**

**A:** No. Retesting confirms that specific case. Checking that everything else still works is a different activity, called regression testing.

---

## 7. Test Objective

**Q: What is a test objective?**

**A:** It is the reason or the purpose for which you are doing a test. It answers a very basic question: "What do we want to achieve or demonstrate by running this test?" It is the WHY — not the what (scenario) and not the how (case).

**Q: How do you know if a test objective is good?**

**A:** If you can write it as a question that can actually be answered, and if you know when you are done.

**Q: What is the formula to write one?**

**A:** Action verb + which component or flow + under which condition or rule. For example: "Verify that the exported inventory file keeps the same data as the screen, with 200 items loaded."

**Q: What is the difference between a test objective, a test scenario and a test case?**

**A:** The objective is WHY we test — the question we want to answer. The scenario is WHAT we test — the area or flow. The case is HOW we test it — the steps, the data and the expected result.

**Q: Give an example of a bad test objective and fix it.**

**A:** Bad: "Test the photo upload so it works." Fixed: "Validate that the system rejects a photo larger than 2 MB without crashing." A good objective targets the risk, not just the happy path.

**Q: Why is "everything works correctly" not a test objective?**

**A:** Because it gives no direction. It is like saying the objective of building a building is "that it doesn't fall down". It is not a question that can be answered, and it does not tell you when you are done.
