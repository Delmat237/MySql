Pour débuter avec MySQL sur Ubuntu, voici les étapes principales :

# 1. Installer MySQL
    Sur Ubuntu, MySQL peut être installé via apt. Pour installer MySQL Server, exécutez la commande suivante dans un terminal :

    sudo apt update
    sudo apt install mysql-server
Cela installera MySQL et ses dépendances.

#  2. Sécuriser l’installation

Après l’installation, il est recommandé d’exécuter le script de sécurité de MySQL :

sudo mysql_secure_installation

Ce script vous posera plusieurs questions, notamment :

    Configurer un mot de passe root (pour MySQL 5.7 et versions antérieures).
    Supprimer les utilisateurs anonymes.
    Interdire l’accès root à distance.
    Supprimer la base de test.

Suivez les recommandations pour sécuriser votre installation.

# 3. Vérifier que MySQL fonctionne

Après l’installation, MySQL démarre automatiquement. Pour vérifier son statut :

sudo systemctl status mysql

Si MySQL n’est pas en cours d’exécution, démarrez-le avec :

sudo systemctl start mysql

Pour qu’il démarre automatiquement au démarrage du système :

sudo systemctl enable mysql

# 4. Accéder à MySQL

Pour accéder à la console MySQL en tant que root :

sudo mysql

Si MySQL est configuré pour exiger un mot de passe root :

mysql -u root -p

Entrez le mot de passe que vous avez défini lors de l’installation.
# 5. Créer une base de données et un utilisateur

Une fois connecté à MySQL, vous pouvez créer une base de données et un utilisateur :

CREATE DATABASE test_db;
CREATE USER 'test_user'@'localhost' IDENTIFIED BY 'mot_de_passe';
GRANT ALL PRIVILEGES ON test_db.* TO 'test_user'@'localhost';
FLUSH PRIVILEGES;

# 6. Tester la connexion avec l’utilisateur créé

Quittez MySQL avec exit et reconnectez-vous avec le nouvel utilisateur :

mysql -u test_user -p

# 7. Installer MySQL Workbench (optionnel)

Si vous souhaitez une interface graphique pour gérer MySQL :

sudo apt install mysql-workbench

Lancez ensuite MySQL Workbench depuis le menu ou avec :

mysql-workbench

Avec ces étapes, vous avez une installation fonctionnelle de MySQL sur Ubuntu. Tu as des questions ou tu veux une configuration plus avancée ? 😊
