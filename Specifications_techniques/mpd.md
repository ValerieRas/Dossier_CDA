# Modèle Physique de données MPD

## Introduction 

Un Modèle Physique de Données (MPD) est une représentation détaillée des données dans une base de données, prenant en compte les contraintes techniques et les caractéristiques spécifiques du système de gestion de base de données (SGBD) utilisé.  
Il inclut les tables, les colonnes, les types de données, les index, et les contraintes de clé primaire et étrangère. 

Pour **Keep This**, le MPD détaillera la création des tables Users, Notes, Notebooks, Friends-Users, Status, et NoteSharing, en spécifiant les types de données exacts (par exemple, VARCHAR, TEXT, DATETIME) et les contraintes d'intégrité (comme les clés primaires et étrangères, les contraintes de non-nullité, et les contraintes uniques). 

## Script de la BDD

```sql
CREATE TABLE Users(
    id_user VARCHAR(36) ,
    nom_user VARCHAR(50)  NOT NULL,
    certified_email_user VARCHAR(100) ,
    temp_email_user VARCHAR(100)  NOT NULL,
    password_user VARCHAR(100)  NOT NULL,
    salt_user VARCHAR(100)  NOT NULL,
    created_at TIMESTAMP NOT NULL,
    is_active BOOLEAN NOT NULL,
    PRIMARY KEY(id_user)
);

CREATE TABLE notes(
    id_note SERIAL,
    create_at TIMESTAMP NOT NULL,
    content_content TEXT NOT NULL,
    update_at TIMESTAMP NOT NULL,
    archived_at TIMESTAMP NOT NULL,
    status_note VARCHAR(50) ,
    id_user VARCHAR(36) ,
    PRIMARY KEY(id_note),
    FOREIGN KEY(id_user) REFERENCES Users(id_user)
);

CREATE TABLE notebooks(
    id_notebook SERIAL,
    title_notebook VARCHAR(50) ,
    created_at TIMESTAMP NOT NULL,
    id_user VARCHAR(36) ,
    PRIMARY KEY(id_notebook),
    FOREIGN KEY(id_user) REFERENCES Users(id_user)
);

CREATE TABLE admin(
    id_admin VARCHAR(36) ,
    name_admin VARCHAR(50)  NOT NULL,
    email_admin VARCHAR(100)  NOT NULL,
    password_admin VARCHAR(100)  NOT NULL,
    salt_admin VARCHAR(100)  NOT NULL,
    PRIMARY KEY(id_admin)
);

CREATE TABLE authentification_tokens(
    token VARCHAR(100) ,
    timestamp_token TIMESTAMP NOT NULL,
    id_user VARCHAR(36) ,
    PRIMARY KEY(token),
    FOREIGN KEY(id_user) REFERENCES Users(id_user)
);

CREATE TABLE friendships(
    Id_friendship SERIAL,
    id_acceptor VARCHAR(36) ,
    id_requestor VARCHAR(36) ,
    PRIMARY KEY(Id_friendship),
    FOREIGN KEY(id_acceptor) REFERENCES Users(id_user),
    FOREIGN KEY(id_requestor) REFERENCES Users(id_user)
);

CREATE TABLE share_status(
    title_status VARCHAR(50) ,
    PRIMARY KEY(title_status)
);

CREATE TABLE note_versions(
    id_note_versions SERIAL,
    created_at TIMESTAMP NOT NULL,
    note_content TEXT NOT NULL,
    id_note INTEGER NOT NULL,
    PRIMARY KEY(id_note_versions),
    FOREIGN KEY(id_note) REFERENCES notes(id_note)
);

CREATE TABLE sharing(
    id_pooling SERIAL,
    id_note INTEGER,
    title_status VARCHAR(50) ,
    id_user VARCHAR(36) ,
    PRIMARY KEY(id_pooling),
    FOREIGN KEY(id_note) REFERENCES notes(id_note),
    FOREIGN KEY(title_status) REFERENCES share_status(title_status),
    FOREIGN KEY(id_user) REFERENCES Users(id_user)
);

CREATE TABLE contain(
    id_note INTEGER,
    id_notebook INTEGER,
    PRIMARY KEY(id_note, id_notebook),
    FOREIGN KEY(id_note) REFERENCES notes(id_note),
    FOREIGN KEY(id_notebook) REFERENCES notebooks(id_notebook)
);

```
