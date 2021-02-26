import win32com.client as client

# startup outlook instance
outlook = client.Dispatch('Outlook.Application')

# get namespace so that we can access folders
namespace = outlook.GetNameSpace('MAPI')

# get the inbox folder, specifically
inbox = namespace.GetDefaultFolder(6)

# by index starting at zero
subfolder = inbox.Folders[0]
subfoldersub = subfolder.Folders[0]

# filter messages with a body that includes a specific term
sla_messages = [message for message in inbox.Items if 'breach' in message.Body.lower()]

# move the messages to the subfoldersub
for message in sla_messages:
    message.Move(subfoldersub)
