CREATE DATABASE vocab_app_db
CHARACTER SET utf8mb4
COLLATE utf8mb4_general_ci;

USE vocab_app_db;

CREATE TABLE vocab_types(
id int PRIMARY KEY,
name VARCHAR(20) UNIQUE NOT NULL
);

CREATE TABLE vocabs(
id int PRIMARY KEY AUTO_INCREMENT,
word VARCHAR(50) NOT NULL,
meaning VARCHAR(255) NOT NULL,
type_id int NOT NULL,
registered_at DATETIME NOT NULL,
updated_at DATETIME NOT NULL
);

INSERT INTO vocab_types VALUES
(1,"名詞"),
(2,"動詞"),
(3,"形容詞"),
(4,"その他");

INSERT INTO vocabs VALUES
(NULL,"data","データ。単数形はdayum",1,NOW(),NOW()),
(NULL,"clickable","クリックすることができる",3,NOW(),NOW()),
(NULL,"instantiable","インスタンス化する",2,NOW(),NOW()),
(NULL,"duplicate","複製。動詞としても使える",1,NOW(),NOW()),
(NULL,"authenticate","本物であることを確認する。認証する",2,NOW(),NOW()),
(NULL,"authorize","許可する",2,NOW(),NOW()),
(NULL,"query","質問。データベースに対する検索要求。動詞としても使える",1,NOW(),NOW()),
(NULL,"dynamic","ダイナミックな。動的な",3,NOW(),NOW()),
(NULL,"static","静止した。静的な",3,NOW(),NOW()),
(NULL,"deploy","配備する",2,NOW(),NOW());
