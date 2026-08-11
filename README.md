# Celestial Bodies Database 🌌

A PostgreSQL database project tracking interstellar entities for the **freeCodeCamp Relational Database Certification**.

### Design preview for the Celestial Bodies Database Certification Project.

| Database Schema Map Overview                       | Terminal Console Environment                  |
| :------------------------------------------------- | :-------------------------------------------- |
| ![Schema View](images/database-schema-preview.png) | ![Terminal View](images/terminal-preview.png) |

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
  - [Features](features)
  - [How to Run the Project Locally](#how-to-run-the-project-locally)
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

### Screenshot

|             Schema Grid View             | CLI Query View 1 | CLI Query View 2 |
| :--------------------------------------: | :--------------: | :--------------: |
| ![Schema Map](images/schema-version.png) |    ![CLI 1]()    |    ![CLI 2]()    |

### Links

- Solution URL: [GitHub Repository](https://github.com/naftalmambo/celestial-bodies-database)
- Live Site URL: [Live Project Terminal Dump](https://raw.githubusercontent.com/naftalmambo/celestial-bodies-database/refs/heads/main/universe.sql)

### Features

- **5 Distinct Relational Tables:** Fully normalized database tree setup spanning constellations, galaxies, stars, planets, and moons.
- **Proper Primary/Foreign Key Constraints:** Solid relational connections enforcing tight data validation constraints.
- **Linux CLI-Based Interaction:** Built entirely using native terminal scripts and managed straight from the command line.

### How to Run the Project Locally

Follow these simple steps to set up this database on your computer:

1.  **What You Need:** Install PostgreSQL and Git.
2.  **Clone the Project:** `git clone https://github.com/naftalmambo/celestial-bodies-database`
3.  **Rebuild the Database:**
    ```bash
    psql -U freecodecamp -d postgres -c "CREATE DATABASE universe;"
    psql -U freecodecamp -d universe < universe.sql
    ```
4.  **Check the Data:** `psql -U freecodecamp -d universe`

### Built with:

- **PostgreSQL Database Engine** - Used to store, index, and organize interstellar data profiles.
- **Structured Query Language (SQL)** - Used to write relation schema logic, constraints, and constraints trees.
- **VS Code** - My primary text editor for managing configuration scripts and documentation.
- **Linux (Xubuntu via VirtualBox)** - My development environment for running the native project console.

### What I learned from this work

This project helped me understand how databases work behind the scenes. Here are the main things I learned while building this schema:

#### **1. Creating Tables with the Right Data Types**

I learned how to set up columns with specific rules so the database only accepts the correct information. For example, I used `integer` for IDs, `text` for long descriptions, and `character varying(50)` to limit name lengths. I also added `NOT NULL` so important fields cannot be left empty.

```sql
CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying(50) NOT NULL,
    has_planets boolean,
    description text,
    galaxy_id integer
);
```

#### **2. Linking Tables and Adding Security Rules**

I learned how to connect different tables together using Foreign Keys so that a star always belongs to a galaxy. I also learned how to use `ALTER TABLE` to add `UNIQUE` rules, which stops the database from accidentally creating two things with the exact same name.

```sql
-- Making sure two stars cannot have the same name
ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_name_key UNIQUE (name);

-- Connecting the star table to the galaxy table
ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);
```

#### **3. Adding Lots of Data quickly with COPY**

Instead of typing out separate `INSERT INTO` commands for every single row, I learned how to use `COPY FROM stdin`. This is a much faster way to load a big block of rows (like my star data for the Sun, Sirius, and Alpheratz) directly into the database at once.

```sql
COPY public.star (star_id, name, has_planets, description, galaxy_id) FROM stdin;
1	Sun	t	The center star of our home solar system.	1
2	Sirius	f	The brightest star visible in our night sky.	1
3	Alpheratz	t	A bright binary star system.	2
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
