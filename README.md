import os
import random
import datetime
import time

# List of random commit messages
messages = [
    "Updating progress 🚀",
    "Working on something cool 💡",
    "Keeping the streak alive 🔥",
    "Small improvement 🛠",
    "Daily update 📅",
    "Refactoring code ✨",
    "Pushing some changes 💻",
    "Maintenance update 🔧",
    "Code tweak ⚡",
    "New idea implemented 💭",
    "Optimizing performance 🚄",
    "Fixing minor issues 🐛",
    "Polishing code ✨",
    "Testing new features 🧪",
    "Improving stability 🔒"
]

# Number of commits you want to make
commit_count = 5

for i in range(commit_count):
    msg = random.choice(messages)
    
    # Append to log file
    with open("activity_log.txt", "a", encoding="utf-8") as f:
        f.write(f"{datetime.datetime.now()}: {msg}\n")
    
    # Run git commands
    os.system("git add activity_log.txt")
    os.system(f'git commit -m "{msg}"')
    
    print(f"✅ Commit {i+1}/{commit_count} with message: {msg}")
    
    # Small delay so commits have different timestamps
    time.sleep(2)

# Push all commits at once
os.system("git push")
print("🚀 All commits pushed successfully!")

