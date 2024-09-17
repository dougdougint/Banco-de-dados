-- 1. Criar o Banco de Dados
CREATE DATABASE IF NOT EXISTS ctg_eventos;
USE ctg_eventos;

-- 2. Criar Tabelas

-- Tabela: Eventos
CREATE TABLE IF NOT EXISTS Eventos (
    evento_id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    data DATE NOT NULL,
    local VARCHAR(255),
    descricao TEXT
);

-- Tabela: Participantes
CREATE TABLE IF NOT EXISTS Participantes (
    participante_id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    idade INT,
    genero ENUM('Masculino', 'Feminino', 'Outro'),
    escolaridade ENUM('Fundamental', 'Médio', 'Superior', 'Pós-graduação'),
    contato VARCHAR(255)
);

-- Tabela: Feedback
CREATE TABLE IF NOT EXISTS Feedback (
    feedback_id INT AUTO_INCREMENT PRIMARY KEY,
    evento_id INT,
    participante_id INT,
    avaliacao INT,
    comentario TEXT,
    FOREIGN KEY (evento_id) REFERENCES Eventos(evento_id),
    FOREIGN KEY (participante_id) REFERENCES Participantes(participante_id)
);

-- 3. Inserir Dados

-- Inserir Eventos
INSERT INTO Eventos (nome, data, local, descricao)
VALUES 
('Rodeio', '2024-06-15', 'Rua Borges de Medeiros, 663', 'Evento tradicional com competições e shows de rodeio.'),
('Show de Música Gaúcha', '2024-07-20', 'Rua Borges de Medeiros, 663', 'Show com bandas locais e danças típicas.');

-- Inserir Participantes
INSERT INTO Participantes (nome, idade, genero, escolaridade, contato)
VALUES 
('João Silva', 30, 'Masculino', 'Superior', 'joao.silva@example.com'),
('Maria Oliveira', 45, 'Feminino', 'Médio', 'maria.oliveira@example.com');

-- Inserir Feedback
INSERT INTO Feedback (evento_id, participante_id, avaliacao, comentario)
VALUES 
(1, 1, 4, 'Ótimo rodeio!'),
(2, 2, 5, 'Show incrível!');

-- 4. Consultas Exemplares

-- Consultar Todos os Eventos
SELECT * FROM Eventos;

-- Consultar Participantes por Evento
SELECT p.nome, f.avaliacao, f.comentario
FROM Feedback f
JOIN Participantes p ON f.participante_id = p.participante_id
WHERE f.evento_id = 1;  -- Troque o ID 
