# 📱 FlowCraft

> Plan, visualize, and design mobile applications before writing code.

FlowCraft is a Flutter + Firebase powered planning platform that helps developers transform app ideas into structured implementation blueprints.

Instead of jumping directly into development, developers can:

- Create projects
- Define application screens
- Build navigation flows
- Create low-fidelity wireframes
- Document implementation notes
- Visualize complete app architecture

All in one place.

---
## Link to web app: https://shashisingh8434.github.io/FlowCraft

## ✨ Why FlowCraft?

Most developers use:

- Paper sketches
- Whiteboards
- Notion pages
- Random diagrams
- Verbal explanations

to communicate app ideas.

FlowCraft brings the entire planning process into a dedicated platform designed specifically for mobile app development.

---
## 📸 Screenshots

<table>
<tr>
<td><img src="https://github.com/user-attachments/assets/226b2d7e-e02c-44a9-bcad-8c3286614c12" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/bc9873c7-5bac-4515-b021-eadba89ba6cd" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/799e5f0a-1930-41c5-9668-3206b6021249" width="250"/></td>
</tr>

<tr>
<td><img src="https://github.com/user-attachments/assets/b4169afc-15e0-4f23-997a-17afccd5329f" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/309e2481-441b-4f1a-8076-df4030683786" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/76bc0321-4071-4504-8972-18ceeafd4c97" width="250"/></td>
</tr>

<tr>
<td><img src="https://github.com/user-attachments/assets/4b73f8b5-8fde-4b6f-b04c-75d3a224ae1a" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/861a89bf-0a1f-4665-a78f-9cb9a258ee05" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/356e8c4b-216d-491b-819b-debcd95b0b9a" width="250"/></td>
</tr>

<tr>
<td><img src="https://github.com/user-attachments/assets/c6b14fb0-a726-4970-8314-31e7cf81ff32" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/71545c1e-454a-4cec-b9c2-8002854f1ac0" width="250"/></td>
<td><img src="https://github.com/user-attachments/assets/0e351734-db1a-4b6d-8d4c-94eb4dc35354" width="250"/></td>
</tr>
</table>
---

# Video

https://github.com/user-attachments/assets/4e9fc946-4142-4f7d-a95c-99e5a9b29a42

---

# 🚀 Features

## 🔐 Authentication

- Google Sign-In
- Firebase Authentication
- Automatic user onboarding
- Protected routes
- Secure project ownership

---

## 📂 Project Management

Organize multiple application ideas.

### Features

- Create Projects
- Edit Projects
- Delete Projects
- Search Projects
- Real-time Firestore Sync

Each project stores:

- Name
- Description
- Owner Information
- Screen Count
- Connection Count
- Timestamps

---

## 📄 Screen Management

Define application screens before implementation.

Examples:

```text
Splash
Login
Signup
Dashboard
Profile
Settings
```

### Features

- Create Screens
- Edit Screens
- Delete Screens
- Reorder Screens
- Screen Details View

---

## 🔗 Navigation Flow Planning

Build relationships between screens and map application navigation.

Example:

```text
Splash
   │
   ▼
Login
   │
   ▼
Dashboard
  / \
 ▼   ▼
Profile Settings
```

### Features

- Create Connections
- Delete Connections
- Prevent Self Connections
- Prevent Duplicate Connections

---

## 📝 Screen Notes

Attach implementation notes directly to screens.

Example:

```text
Login Screen

- Use Google Sign In
- Add validation
- Handle loading state
- Handle network failures
```

### Features

- Create Notes
- Edit Notes
- Delete Notes
- Real-time Sync

---

# 🌐 Infinite Canvas Flow Diagram

Visualize the entire application architecture.

### Features

- Infinite Canvas
- Zoom & Pan
- Persistent Node Positions
- Draggable Screens
- Directional Connections
- Custom Graph Rendering
- Stable Layouts
- Disconnected Screen Support

Unlike traditional generated flowcharts, node positions remain exactly where the user places them.

---

# 🎨 Screen Designer

Create low-fidelity wireframes for individual screens.

### Purpose

Quickly sketch UI layouts before development begins.

### Supported Components

- Text
- Button
- TextField
- Card
- Divider
- Image Placeholder
- List Placeholder
- Scroll Placeholder

### Features

- Drag Components
- Resize Components
- Rename Components
- Delete Components
- Phone Preview Canvas
- Firestore Persistence

Example workflow:

```text
Project
   ↓
Screen
   ↓
Designer
   ↓
Wireframe
```

---

# 🏗️ Architecture

The project follows a feature-first architecture.

```text
lib/
│
├── core/
│   ├── providers/
│   ├── router/
│   └── theme/
│
├── features/
│   ├── auth/
│   ├── dashboard/
│   ├── projects/
│   ├── screens/
│   ├── connections/
│   ├── notes/
│   └── designer/
│
├── shared/
│   └── widgets/
│
└── main.dart
```

---
# 🔥 Firestore Database Structure

The application uses two top-level collections:

```text
users
projects
```

All application data is organized under these collections.

---

## 🌳 Complete Firestore Hierarchy

```text
Firestore
│
├── users
│   └── {uid}
│       ├── uid
│       ├── name
│       ├── email
│       └── createdAt
│
└── projects
    └── {projectId}
        ├── name
        ├── description
        ├── ownerUid
        ├── ownerName
        ├── screenCount
        ├── connectionCount
        ├── createdAt
        ├── updatedAt
        │
        ├── screens
        │   └── {screenId}
        │       ├── name
        │       ├── description
        │       ├── order
        │       ├── x
        │       ├── y
        │       ├── notesCount
        │       ├── incomingCount
        │       ├── outgoingCount
        │       ├── createdAt
        │       ├── updatedAt
        │       │
        │       ├── notes
        │       │   └── {noteId}
        │       │       ├── content
        │       │       ├── createdAt
        │       │       ├── updatedAt
        │       │       └── createdBy
        │       │
        │       └── components
        │           └── {componentId}
        │               ├── type
        │               ├── label
        │               ├── x
        │               ├── y
        │               ├── width
        │               ├── height
        │               ├── createdAt
        │               └── updatedAt
        │
        └── connections
            └── {connectionId}
                ├── sourceScreenId
                ├── sourceScreenName
                ├── targetScreenId
                ├── targetScreenName
                ├── label
                ├── createdBy
                └── createdAt
```

---

## 👤 Users Collection

```text
users
└── {uid}
    ├── uid
    ├── name
    ├── email
    └── createdAt
```

### Fields

| Field     | Type      |
| --------- | --------- |
| uid       | String    |
| name      | String    |
| email     | String    |
| createdAt | Timestamp |

---

## 📂 Projects Collection

```text
projects
└── {projectId}
    ├── name
    ├── description
    ├── ownerUid
    ├── ownerName
    ├── screenCount
    ├── connectionCount
    ├── createdAt
    └── updatedAt
```

### Fields

| Field           | Type      |
| --------------- | --------- |
| name            | String    |
| description     | String    |
| ownerUid        | String    |
| ownerName       | String    |
| screenCount     | Integer   |
| connectionCount | Integer   |
| createdAt       | Timestamp |
| updatedAt       | Timestamp |

---

## 📱 Screens Subcollection

```text
projects
└── {projectId}
    └── screens
        └── {screenId}
```

### Fields

| Field         | Type      |
| ------------- | --------- |
| name          | String    |
| description   | String    |
| order         | Integer   |
| x             | Double    |
| y             | Double    |
| notesCount    | Integer   |
| incomingCount | Integer   |
| outgoingCount | Integer   |
| createdAt     | Timestamp |
| updatedAt     | Timestamp |

---

## 🔗 Connections Subcollection

```text
projects
└── {projectId}
    └── connections
        └── {connectionId}
```

### Fields

| Field            | Type      |
| ---------------- | --------- |
| sourceScreenId   | String    |
| sourceScreenName | String    |
| targetScreenId   | String    |
| targetScreenName | String    |
| label            | String    |
| createdBy        | String    |
| createdAt        | Timestamp |

---

## 📝 Notes Subcollection

```text
projects
└── {projectId}
    └── screens
        └── {screenId}
            └── notes
                └── {noteId}
```

### Fields

| Field     | Type      |
| --------- | --------- |
| content   | String    |
| createdAt | Timestamp |
| updatedAt | Timestamp |
| createdBy | String    |

---

## 🎨 Designer Components Subcollection

```text
projects
└── {projectId}
    └── screens
        └── {screenId}
            └── components
                └── {componentId}
```

### Fields

| Field     | Type      |
| --------- | --------- |
| type      | String    |
| label     | String    |
| x         | Double    |
| y         | Double    |
| width     | Double    |
| height    | Double    |
| createdAt | Timestamp |
| updatedAt | Timestamp |

---

# ⚙️ Tech Stack

| Category           | Technology                 |
| ------------------ | -------------------------- |
| Framework          | Flutter                    |
| Language           | Dart                       |
| Design System      | Material 3                 |
| State Management   | Riverpod                   |
| Authentication     | Firebase Authentication    |
| Database           | Cloud Firestore            |
| Routing            | Go Router                  |
| Architecture       | Feature-First Architecture |
| Data Layer         | Service Layer Pattern      |
| Realtime Updates   | Firestore Streams          |
| Flow Visualization | Custom Graph Renderer      |
| Canvas System      | InteractiveViewer          |
| Wireframing        | Visual Screen Designer     |
| Version Control    | Git & GitHub               |
| Platform Support   | Android, iOS |

```
```

# 🛣️ Roadmap

## Completed

- Authentication
- Projects
- Screens
- Notes
- Connections
- Infinite Flow Diagram
- Visual Screen Designer

## Planned

- Screen States
- Component Actions
- Flow ↔ UI Linking
- Export to JSON
- Export Documentation
- AI Flow Generation
- AI Screen Suggestions

---

# 🎯 Vision

FlowCraft aims to become a developer-first planning platform where developers can:

1. Design mobile application architecture
2. Visualize user journeys
3. Create screen wireframes
4. Document implementation details
5. Generate development blueprints

before writing a single line of production code.

---

# 👨‍💻 Author

## _**Shashi Singh**_

Built with Flutter ❤️
