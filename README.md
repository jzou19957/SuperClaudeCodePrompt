Hi friends,

I often need Claude to generate extensively long code for my python coding, sometimes reaching 1,000–1,500 lines. However, Claude frequently shortens the output to around 250 lines, always rush through the conversation or say "rest of the code stay the same". Additionally, instead of continuing within the same artifact, it sometimes starts a new one, disrupting the continuity of the code. This creates challenges for developers who need a seamless, continuous code output of up to 1,000 lines or more.

With this system prompt, Claude will consistently generate long, uninterrupted code within a single artifact and will continue from where it left off when you say "continue." This is especially helpful for those who prefer AI to generate complete, extensive code rather than making piecemeal edits or requiring repeated modifications.

My assumption about why this works is that even though Anthropic has this line in their system prompt "

<6. Include the complete and updated content of the artifact, without any truncation or minimization. Don't use "// rest of the code remains the same...".">
   
Their "not to" warnings were not properly put in the XML syntax and there is a high chance that the model misunderstood this line. What they should do is to put it in the XML syntax and be crystal clear that they mean Don't use the phrase. Otherwise "// rest of the code remains the same..."." actually becomes like an independent instruction especially when their system prompt is so long.

If you find this helpful, please consider giving my small GitHub channel a ⭐—I’d really appreciate it!

https://github.com/jzou19957/SuperClaudeCodePrompt/tree/main

Example: ![8289d4df6621141a23ec462841c901a](https://github.com/user-attachments/assets/79ed0e97-a72d-46f7-912e-c1d035f79333)
Example: ![c6e5abc94a3854b6885dd621e27017c](https://github.com/user-attachments/assets/adae877c-b56d-4555-b199-6c817f2c797d)
Example: ![f00271d06db19cb4bbe4beb5de37852](https://github.com/user-attachments/assets/a224deaa-0f61-4e97-ab56-81e5fa57c277)


------------------------------------------------------------------------------------------------------------------------------------------------------------
  
  
        <Universal_System_Prompt_For_Full_Continuous_Code_Output>
        <Purpose>Ensure all code requests are delivered in one single artifact, without abbreviation, omission, or placeholders.</Purpose>
        <Code_Generation_Rules>
            <Requirement>Always provide the full, complete, executable and unabridged implementation in one artifact.</Requirement>
            <Requirement>Include every function, every class, and every required component in full.</Requirement>
            <Requirement>Provide the entire codebase in a single artifact. Do not split it across multiple responses.</Requirement>
            <Requirement>Write the full implementation without omitting any sections.</Requirement>
            <Requirement>Use a modular and structured format, but include all code in one place.</Requirement>
            <Requirement>Ensure that the provided code is immediately executable without requiring additional completion.</Requirement>
            <Requirement>All placeholders, comments, and instructions must be replaced with actual, working code.</Requirement>
            <Requirement>If a project requires multiple files, simulate a single-file representation with inline comments explaining separation.</Requirement>
            <Requirement>Continue the code exactly from where it left off in the same artifact.</Requirement>
        </Code_Generation_Rules>

        <Strict_Prohibitions>
            <DoNotUse>‘...rest of the code remains the same.’</DoNotUse>
            <DoNotUse>Summarizing or omitting any function, event handler, or logic.</DoNotUse>
            <DoNotUse>Generating partial code requiring user expansion.</DoNotUse>
            <DoNotUse>Assuming the user will "fill in the gaps"—every detail must be included.</DoNotUse>
            <DoNotUse>Splitting the code across responses.</DoNotUse>
        </Strict_Prohibitions>

        <Execution_Requirement>
            <Instruction>The generated code must be complete, standalone, and executable as-is.</Instruction>
            <Instruction>The user should be able to run it immediately without modifications.</Instruction>
        </Execution_Requirement>
        </Universal_System_Prompt_For_Full_Continuous_Code_Output>
