let emailAppData = {
    userInfo: {
        name: 'John Doe',
        emailAddress: 'john.doe@example.com',
        profilePictureUrl: 'https://example.com/profile.jpg'
    },
    mailboxes: {
        inbox: [
            {
                from: 'jane.doe@example.com',
                to: 'john.doe@example.com',
                subject: 'Meeting Reminder',
                body: 'Don\'t forget about the meeting at 3 PM.',
                date: '2024-06-11T10:30:00',
                isRead: false
            },
            {
                from: 'newsletter@example.com',
                to: 'john.doe@example.com',
                subject: 'Weekly Update',
                body: 'Here are the updates for this week...',
                date: '2024-06-10T08:00:00',
                isRead: true
            }
        ],
        junk: [],
        sent: [
            {
                from: 'john.doe@example.com',
                to: 'jane.doe@example.com',
                subject: 'Re: Meeting Reminder',
                body: 'Got it, thanks!',
                date: '2024-06-11T10:35:00',
                isRead: true
            }
        ],
        drafts: [
            {
                from: 'john.doe@example.com',
                to: '',
                subject: 'Draft Email',
                body: 'This is a draft email...',
                date: '2024-06-11T11:00:00',
                isRead: false
            }
        ],
        trash: []
    },
    contacts: [
        {
            name: 'Jane Doe',
            email: 'jane.doe@example.com',
            lastMessage: 'Don\'t forget about the meeting at 3 PM.'
        },
        {
            name: 'Newsletter',
            email: 'newsletter@example.com',
            lastMessage: 'Here are the updates for this week...'
        }
    ]
};

// Get a list of mailbox names
let mailboxNames = Object.keys(emailAppData.mailboxes);
console.log(mailboxNames); // Output: ["inbox", "junk", "sent", "drafts", "trash"]

// Get a list of emails in the inbox
let inboxEmails = emailAppData.mailboxes.inbox;
console.log(inboxEmails); // Output: [{from: 'jane.doe@example.com', ...}, {from: 'newsletter@example.com', ...}]

// Get the text of the second email in the inbox
let secondEmailBody = emailAppData.mailboxes.inbox[1].body;
console.log(secondEmailBody); // Output: "Here are the updates for this week..."

// Mark an email as sent
emailAppData.mailboxes.sent.push(emailAppData.mailboxes.drafts[0]);
emailAppData.mailboxes.drafts.splice(0, 1);
console.log(emailAppData.mailboxes.sent); // Output: [{from: 'john.doe@example.com', ...}, {from: 'john.doe@example.com', ...}]
console.log(emailAppData.mailboxes.drafts); // Output: []

// Add a draft email to the drafts mailbox
let newDraftEmail = {
    from: 'john.doe@example.com',
    to: 'someone@example.com',
    subject: 'New Draft',
    body: 'This is a new draft email.',
    date: '2024-06-11T12:00:00',
    isRead: false
};
emailAppData.mailboxes.drafts.push(newDraftEmail);
console.log(emailAppData.mailboxes.drafts); // Output: [{from: 'john.doe@example.com', ...}
