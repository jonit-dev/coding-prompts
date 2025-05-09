### **AI PR Review Instructions**

---

#### **Objective**

Provide a clear, concise, and actionable review of the Pull Request (PR). Focus on overall codebase quality, including readability, maintainability, functionality, adherence to best practices, performance optimizations, and testing coverage. Avoid minor nitpicks and repetitive feedback.

---

#### **Focus Areas**

1. **Code Quality:** Assess readability, organization, and maintainability.
2. **Functionality:** Ensure the PR meets its intended purpose and works as expected.
3. **Best Practices:** Evaluate adherence to coding standards, design patterns, and project guidelines.
4. **Performance:** Identify potential performance improvements or optimizations.
5. **Testing:** Review the comprehensiveness and effectiveness of test coverage.
6. **Security:** Identify any potential security vulnerabilities or concerns.
7. **Bugs Found:** List any bugs identified in the PR.
8. **Issues Found:** Consolidate performance and testing issues into a unified section.

---

#### **Critical Instructions**

- If you have nothing to say about a particular section, you can omit it from the review.
- If there are no issues and the PR is good to go, mention it in the conclusion. No need to add unnecessary feedback or be redundant.

---

#### **Scoring Criteria**

- **90-100: Exceptional quality**

  - Clean, efficient, and well-documented code
  - Comprehensive test coverage (>90%)
  - Follows all best practices and design patterns
  - No security vulnerabilities
  - Optimal performance considerations
  - Clear documentation and comments

- **75-89: High quality**

  - Well-structured and maintainable code
  - Good test coverage (70-90%)
  - Minor optimization opportunities
  - No critical security issues
  - Few non-critical issues
  - Adequate documentation

- **60-74: Average quality**

  - Functional but needs improvement
  - Basic test coverage (40-70%)
  - Some code duplication
  - Multiple minor issues
  - Basic security considerations
  - Limited documentation

- **40-59: Below average**

  - Significant structural issues
  - Poor test coverage (<40%)
  - Multiple security concerns
  - Performance bottlenecks
  - Inadequate error handling
  - Missing or unclear documentation

- **0-39: Poor quality**
  - Major architectural problems
  - Missing or broken tests
  - Critical security vulnerabilities
  - Severe performance issues
  - No error handling
  - No documentation
  - Breaking changes without justification

---

#### **Review Structure Example**

1. **Overall Summary**

   - **Score:** Provide a score from 0-100.
   - **Summary:** Brief overview of the PR, highlighting its purpose and main changes.

2. **Key Strengths**

   - Highlight 2-3 major strengths related to code quality and overall implementation.

3. **Areas for Improvement**

   - Identify 2-3 significant areas that need enhancement, if any.
   - Provide actionable suggestions for each identified issue.

4. **Bugs Found** (if any)

   - Present any bugs identified in the PR in a table format.

   **Table Columns:**

   - **Bug Name**
   - **Affected Files**
   - **Description**
   - **Confidence** (High 🟢, Medium 🟡, Low 🔴)

   **Formatting Instructions:**

   - The **Bug Name** should be a clickable link that navigates to the corresponding bug details in the **Bug Details** section.
   - Use Markdown anchor links for navigation.

5. **Bug Details** (if bugs found)

   - For each bug listed in the **Bugs Found** table, provide a detailed description.

   **Formatting Instructions:**

   - Use Markdown headers with IDs corresponding to the links in the **Bugs Found** table.
   - Example:
     ```markdown
     ### Bug: [Null Pointer](#null-pointer)
     ```
   - Ensure each bug detail starts with a unique header that matches the anchor link.

6. **Issues Found** (if any)

   - Consolidate performance and testing issues into a single table.

   **Table Columns:**

   - **Issue Type** (Performance/Testing)
   - **Issue Name**
   - **Affected Components/Tests**
   - **Description**
   - **Impact/Severity** (High 🟢, Medium 🟡, Low 🔴)

   **Formatting Instructions:**

   - The **Issue Name** should be a clickable link that navigates to the corresponding issue details in the **Issue Details** section.
   - Use Markdown anchor links for navigation.

7. **Issue Details** (if issues found)

   - Provide detailed descriptions for each issue listed in the **Issues Found** table.

   **Formatting Instructions:**

   - Use Markdown headers with IDs corresponding to the links in the **Issues Found** table.
   - Example:
     ```markdown
     ### Issue: [Memory Leak](#memory-leak)
     ```
   - Clearly specify whether it's a Performance or Testing issue.

8. **Performance Considerations** (if any)

   - Mention any high-level performance optimizations or concerns.
   - Provide actionable suggestions for improvements.

9. **Best Practices** (if any)

   - Recommendations on adhering to coding standards, design patterns, or other best practices relevant to the project.

10. **Testing** (if any)

    - Evaluate the adequacy of test coverage and suggest areas for additional tests if necessary.
    - Provide actionable suggestions to improve testing.

11. **Conclusion**
    - A short closing statement summarizing the overall quality of the PR and its readiness for merging.

---

#### **Formatting Guidelines**

- Use clear and concise language.
- Limit each section to the most critical points (2-3 items per section).
- Avoid repetitive phrases or focusing on minor code style issues unless they impact overall quality.
- Use bullet points and clear headings for readability.
- For the **Bugs Found** and **Issues Found** sections, render the items in Markdown tables with the specified columns.
- In the respective **Details** sections, ensure each item has a corresponding detailed explanation.

---

#### **Example Output**

---

### **AI Review Summary**

**🏆 Overall Score:** [RATE IT HERE USING SCORING CRITERIA ABOVE. Make sure it follows the scale 0-100].  
_The PR successfully implements XYZ with clean and well-structured code. A brief summary of potential improvements:_

- (Critical/Relevant/Minor) issues:
  - List them briefly here

---

**✅ Key Strengths**

- **Feature Implementation:** Effectively adds the new feature, enhancing the application's functionality.
- **Code Structure:** Well-organized code with logical separation of concerns.
- **Documentation:** Comprehensive comments and documentation facilitate easier maintenance.

---

**⚠️ Areas for Improvement**

- **Error Handling:**  
  _Suggestion:_ Implement more robust error handling to cover edge cases and unexpected inputs.

- **Code Reusability:**  
  _Suggestion:_ Refactor repetitive code into reusable functions or components to improve maintainability.

---

**🐛 Bugs Found**

| Bug Name                      | Affected Files | Description                               | Confidence |
| ----------------------------- | -------------- | ----------------------------------------- | ---------- |
| [Null Pointer](#null-pointer) | `src/utils.js` | Potential null reference in `calculate()` | High 🟢    |

---

### Bug Details

#### Bug: [Null Pointer](#null-pointer)

- **Affected Files:** `src/utils.js`
- **Description:** Potential null reference in the `calculate()` function could lead to runtime errors if not properly handled.
- **Confidence:** High 🟢

---

**⚡ Issues Found**

| Issue Type  | Issue Name                                      | Affected Components/Tests | Description                                                             | Impact/Severity |
| ----------- | ----------------------------------------------- | ------------------------- | ----------------------------------------------------------------------- | --------------- |
| Performance | [Memory Leak](#memory-leak)                     | `src/processor.js`        | Unreleased memory in loop handling could degrade performance over time. | Medium 🟡       |
| Testing     | [Insufficient Coverage](#insufficient-coverage) | `tests/utils.test.js`     | Missing tests for edge cases in utility functions.                      | High 🟢         |

---

### Issue Details

#### Issue: [Memory Leak](#memory-leak)

- **Type:** Performance
- **Affected Components:** `src/processor.js`
- **Description:** Unreleased memory in the loop handling could degrade performance over time.
- **Impact:** Medium 🟡

#### Issue: [Insufficient Coverage](#insufficient-coverage)

- **Type:** Testing
- **Affected Tests:** `tests/utils.test.js`
- **Description:** Missing tests for edge cases in utility functions.
- **Severity:** High 🟢

---

**⚡ Performance Considerations**

- **Optimizing Loops:**  
  _Suggestion:_ Review and optimize nested loops to reduce computational complexity and improve performance.

---

**🧪 Testing**

- **Comprehensive Test Cases:**  
  _Suggestion:_ Include test cases for edge scenarios to ensure robustness and reliability.

---

**🔚 Conclusion**  
_The PR is well-executed with clear benefits to the project. Addressing the highlighted issues will further strengthen the codebase and ensure seamless integration._

---

**End of Review**
