# Processus

Un **Processus** est un programme en cours d'ex�cution auquel est associ�  
un environnement processeur et un environnement m�moire.

# Cr�ation d'un processus

Pour cr�er un processus, sous Windows:
* D�finissez le chemin complet du processus **appName**
* Cr�ez le processus avec la m�thode **CreateProcess()**

# Code source
```
//===============================================
void GProcess::createProcess() {
    wstring m_wsTmp = wstring(m_appName.begin(), m_appName.end());
    LPCWSTR m_ws = m_wsTmp.c_str();

    BOOL m_res = CreateProcess(
                m_ws, NULL, NULL,
                NULL, FALSE, NULL, NULL, NULL, &m_startupInfo,
                &m_processInformation);

    if(m_res == 0) {
        cout << "ERROR : The process isn't created...\n";
        exit(0);
    }

    cout << "SUCCESS : The process is created...\n";
}
//===============================================
```

# R�sultats
![Resultats](https://raw.githubusercontent.com/gkesse/ReadyThread/master/Processus/img/Terminal.png)
![Resultats](https://raw.githubusercontent.com/gkesse/ReadyThread/master/Processus/img/Processus.png)

# Voir Aussi

* [ReadyThread](https://github.com/gkesse/ReadyThread "ReadyThread")  
* [Processus](https://github.com/gkesse/ReadyThread/tree/master/Processus "Processus")  
