# Future Improvements for Custom Commands

Here is a list of ideas to further improve the `/create_blog_post` and `/create_guide` commands.

### 1. Automatic Categorization
Analyze the title of the post and automatically suggest saving the file in a relevant sub-directory. For example, a post with "Azure" in the title could be saved in `blogs/azure/`.

### 2. Front Matter Generation
Automatically generate a complete front matter block for the markdown files. This can include:
- title
- date
- author
- categories
- tags
- meta description

This is particularly useful for static site generators like Jekyll or Hugo.

### 3. AI-Generated Drafts
Instead of just creating a placeholder, the command could generate a full draft of the blog post or guide. The user could provide a few bullet points or an outline, and the AI would expand it into a complete article.

### 4. Interactive Setup
Make the commands interactive. Instead of a single command, the AI could ask a series of questions to gather all the necessary details for the new post, such as:
- Title
- Tags and categories
- Directory to save the file in
- A brief outline of the content
