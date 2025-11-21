# ⏳ Timer Thread em Python com `prompt_toolkit`

Este repositório contém uma série de exemplos que demonstram a criação de uma
classe de **Timer** assíncrona baseada em `threading.Thread` em Python,
culminando em uma aplicação interativa de múltiplos _timers_ usando a biblioteca
`prompt_toolkit`.

A implementação foca em:

1.  **Herança de Thread:** Estendendo `threading.Thread` para encapsular a
    lógica do timer.
2.  **Controle de Fluxo:** Utilização de `threading.Event` (`_stop_event` e
    `_running_event`) para gerenciar os estados **Stop**, **Pause** e
    **Resume**.
3.  **Precisão:** Uso de `time.monotonic_ns` para cálculos de tempo mais
    precisos, compensando o _overhead_ do loop.
4.  **Interface Gráfica:** Construção de uma interface de console interativa com
    `prompt_toolkit` (no exemplo final `code008.py`).

## ⚙️ Como Executar

Para executar o código principal, que demonstra a interface interativa de
múltiplos _timers_, use o seguinte comando no **Linux** ou **macOS**:

```bash
clear ; PYTHON_GIL=1 uv run src/conc_lessons/lesson003/code008.py
`Nota: É crucial definir PYTHON_GIL=1 para garantir que o Global Interpreter Lock (GIL) esteja ativado durante a execução de threads em ambientes que usam o uv (como o uv run), garantindo o comportamento esperado da aplicação multithread. O caminho src/conc_lessons/lesson003/ deve ser ajustado para a estrutura do seu projeto.🔑 Teclas de Atalho na Aplicação Interativa (code008.py):AçãoTimer 1 (45s)Timer 2 (3600s)Timer 3 (2800s)Timer 4 (60s)Pausar/Continuar1234PararF1F2F3F4Sair da AplicaçãoCtrl + QCtrl + QCtrl + QCtrl + Q📁 Arquivos PrincipaisArquivoDescriçãoConceitos Demonstadoscode001.pyExemplo básico de herança de threading.Thread.threading.Thread por herança.code002.pyExtensão da Thread para passar funções alvo (target) e obter um resultado simples.Passagem de target e recuperação de self.result.code003.pyImplementação aprimorada com ParamSpec (typing) para capturar o resultado e exceções.ParamSpec, tratamento de resultados e exceções da Thread.code005.pyIntrodução de threading.Event para gerenciar Pause e Stop do loop principal.Controle de fluxo com Event.set(), Event.clear(), Event.is_set() e Event.wait().code006.pyRefatoração para um Timer funcional com cálculo de tempo preciso (time.monotonic_ns) e compensação de loop overhead.Compensação de Drift (desvio de tempo), time.monotonic_ns.code007.pyVersão do Timer que demonstra a atualização do estado visual no console (interface simples) e uso de threading.Timer para agendar ações.Atualização de console, uso de threading.Timer.code008.pyAplicação Final: Implementa 4 timers paralelos em uma interface interativa usando a biblioteca prompt_toolkit.Threads em IGUIs de terminal (TUI), prompt_toolkit, lambdas para renderização dinâmica de conteúdo.📚 Tecnologias UtilizadasPython: Linguagem principal.threading: Módulo para programação concorrente.time: Módulo para medição de tempo (monotonic_ns, sleep).prompt_toolkit: Biblioteca para construir aplicações de linha de comando interativas (TUI).``
```
