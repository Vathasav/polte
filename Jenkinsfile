pipeline {
    agent any

    stages {
        stage('Build stack') {
            steps {
                echo 'Building heat stack'
                sh '''
                    source env.sh
                    ansible-galaxy -r requirements.yml install
                    ansible-playbook -i inventory site.yml -e "puppet_environment=newton heat_stack_name=testing"
                '''
            }
        }
        stage('Reboot to enforce cloud-init changes') {
            steps {
                echo 'Booting'
            }
        }
        stage('Parallel actions') {
            steps {
                parallel("Bootstrap LDAP server": {
                    echo "LDAP"
                },
                "Bootstrap puppetmaster": {
                    echo "Puppetmaster"
                },
                "Bootstrap API nodes": {
                    echo "APIs"
                })
            }
        }
        stage('Puppetize backend') {
            steps {
                echo 'Puppetizing'
            }
        }
        stage('Puppetize APIs') {
            steps {
                echo 'Puppetizing'
            }
        }
        stage('Post-puppetize actions') {
            steps {
                echo 'Deploying'
            }
        }
    }
}
