<%*
/* BaseNote template
 * Created by: Johnny
 * Derived from: https://forum.obsidian.md/t/new-properties-and-templater-prompts-and-commands/66425/12
 * Last modified: 2023-10-14
 */
 
//Let's be explicit about these variable types for readability
let sTitle = tp.file.title //we populate our own local for consistency
let sSubject = ""
let sCategory = ""
let callBackDelay=200 //in ms
// This seems a little hackish,
// but it is a very convenient way to prevent 
// Untitled-XXX from stacking up", and also is a kind of catch all for whatever keybindings people may opt for
if (sTitle.startsWith("Untitled")) {
sTitle = await tp.system.prompt("New note name");
} await tp.file.rename(sTitle);

//More application specific logic should probably go here:
sCategory = await tp.system.prompt("Category");
sSubject = await tp.system.prompt("Subject");

//Okay, this registers an anonymous callback that will *update* the new notes frontmatter approximately 2/10ths of a sec after completion
setTimeout(() => {
app.fileManager.processFrontMatter(tp.config.target_file, frontmatter => 
{
frontmatter["category"] = sCategory;
frontmatter["subject"] = sSubject;
})

}, callBackDelay) 

  

-%>