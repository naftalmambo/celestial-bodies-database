# Celestial Bodies Database 🌌

A relational database project tracking interstellar entities across a deep-space grid. This project fulfills the core backend data requirements for the **freeCodeCamp Relational Database Certification**.

### Design preview for the Celestial Bodies Database Certification Project.

| Database Schema Map Overview                       | Terminal Console Environment                  |
| :------------------------------------------------- | :-------------------------------------------- |
| ![Schema View](images/database-schema-preview.png) | ![Terminal View](images/terminal-preview.png) |

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
  - [How to Run the Project Locally](#how-to-run-the-project-locally)
  - [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [AI Collaboration](#ai-collaboration)
- [Open for Opportunities & Collaboration](#open-for-opportunities--collaboration)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- Build a relational database tracking 5 distinct interstellar tables matching exact structural criteria
- Map out clear data constraints using Primary Keys, Foreign Keys, Unique attributes, and specific variable scopes
- Run successful multi-table entity join queries from a Linux CLI terminal container matching real-world schema states

### Screenshots

|             Schema Grid View             | CLI Query View 1 | CLI Query View 2 |
| :--------------------------------------: | :--------------: | :--------------: |
| ![Schema Map](images/schema-version.png) |    ![CLI 1]()    |    ![CLI 2]()    |

### Links

- Solution URL: [GitHub Repository](https://github.com/naftalmambo/celestial-bodies-database)
- Live Site URL: [Live Project Terminal Dump](https://raw.githubusercontent.com/naftalmambo/celestial-bodies-database/refs/heads/main/universe.sql)

## How to Run the Project Locally

Follow these simple steps to set up this database on your computer:

### 1. What You Need

Make sure you have **PostgreSQL** and **Git** installed on your machine.

### 2. Clone the Project

Open your terminal and run these commands to download the project files:

```bash
git clone https://github.com
cd celestial-bodies-database
```

### 3. Rebuild the Database

Run these commands to create the database and load all my tables and data from the backup file:

```bash
# Create an empty database named universe
psql -U freecodecamp -d postgres -c "CREATE DATABASE universe;"

# Restore the database using my universe.sql file
psql -U freecodecamp -d universe < universe.sql
```

### 4. Check the Data

To open the PostgreSQL terminal and test queries yourself, run:

```bash
psql -U freecodecamp -d universe
```

## My process

### Built with

- **Relational Database Design Engine**
- **PostgreSQL Engine**
- **Structured Query Language (SQL)**
- **CLI Shell Script Pipeline Workflow**
- **VS Code** - My primary editor for writing clean, structured migration scripts.
- **Linux (Ubuntu/WSL/Docker)** - My development environment for a professional, stable system architecture.
- **Windows Command Prompt (psql Client)** - Used for cross-environment verification to ensure data integrity.

### What I learned from this work

This project was a major milestone in my journey toward mastering responsive database storage frameworks and server-side data control. Here are the key technical concepts I mastered using my exact database schema:

#### **1. Constructing Relational Tables with Data Type Specifications**

I learned how to structure tables professionally with strict constraints using character lengths and specific type rules. In my actual file, I configured the core tables like `star` using explicit `integer`, `text`, and variable character parameters to manage data sizes.

```sql
CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying(50) NOT NULL,
    has_planets boolean,
    description text,
    galaxy_id integer
);
```

#### **2. Enforcing Relational Constraints Post-Creation**

I learned that PostgreSQL dump engines separate the initial table construction from database security layers. I mastered how to use `ALTER TABLE ONLY` commands to append Primary Keys, Unique constraints, and Foreign Key relations to columns like `galaxy_id` after the structures exist.

```sql
-- Enforcing Data Uniqueness on the Name column
ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_name_key UNIQUE (name);

-- Linking the Foreign Key from the Star table back to the Galaxy table
ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);
```

#### **3. High-Velocity Data Ingestion via Terminal Streams**

I learned how to use the raw `COPY FROM stdin` tool to feed complex datasets into my relational architecture instantly. Instead of using dozens of single row insertion loops, this allows seamless seeding of systems like _Sun_, _Sirius_, and _Alpheratz_ along with their boolean metrics (`t`/`f`).

```sql
COPY public.star (star_id, name, has_planets, description, galaxy_id) FROM stdin;
1	Sun	t	The center star of our home solar system.	1
2	Sirius	f	The brightest star visible in our night sky.	1
3	Alpheratz	t	A bright binary star system.	2
\.
```

### Continued development

In future work, I intend to focus on:

- **Database Performance Optimization:** I believe I've tried my best to make this schema as relational and structured as possible using freeCodeCamp architecture standards, while also open to advanced query runtime indexing improvements.

### AI Collaboration

- **Tools Used:** Google AI.

Throughout this project, I used an AI-collaborative workflow to:

- **Refine Logic:** Instead of just copying scripts, I used AI to explain "why" certain field mapping configurations like `NUMERIC(4, 2)` scale better than standard floating points.
- **Master Best Practices:** I learned to implement professional standards such as **uppercase SQL keyword protocols**, **explicit foreign key linking rules**, and clean repository schema layouts.
- **Debugging & Polish:** I collaborated with AI to solve specific sequence generation bugs (like entity primary index mismatches) and to perfect terminal dump processes using standard migration tools.

## Open for Opportunities & Collaboration

This project is part of my journey toward becoming a professional Web Developer and ultimately a Java Full-Stack Engineer. I am currently:

- 🔭 **Open for work:** Looking for junior roles or freelance opportunities where I can apply my skills in Java Core Logic, SQL Relational Structures, and Backend Engineering.
- 🤝 **Open to contribute:** Interested in collaborating on open-source projects or team-based infrastructure tasks.

If you like what you see or have a backend/operations system you need help with, connect with:

**Author**

- [ 💼 LinkedIn](https://www.linkedin.com/in/naftalmambo/)
- [ 💻 GitHub](https://github.com/naftalmambo)
- [ 💬 Discord](https://discordapp.com/users/1157321092482994246)

## Acknowledgments

### 🌟 Appreciation for freeCodeCamp

I want to express my sincere gratitude to **[freeCodeCamp](https://freecodecamp.org)** for providing these incredible, interactive, real-world development challenges that I am sure will enable me to grow to be the developer I aspire to be.

This platform is more than just a place to practice syntax, it is a gateway to building skills that truly **change lives**.

By bridging the gap between classroom theory and enterprise command-line environments, freeCodeCamp helps me build a rock-solid tech foundation for a future where I can create meaningful digital systems.
