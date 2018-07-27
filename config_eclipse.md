### Novo Projeto

- Clonar esse repositório com nome do projeto desejado.
- Rodar o Eclipse. File > Import.
- Escolher "C/C++ > Existing Code as Makefile Project", next.
- "Existing Code Location" (diretório do repositório clonado, deve conter o makefile do projeto).
- Em "Toolchain for Indexer Settings" escolher "Cross GCC".

### Propriedades do projeto.

- Botão direito no projeto criado no eclipse.
- Em  "C/C++ Build > Environment" add variável ```BATCH_BUILD``` com valor ```1```.
- Adicionar ```IDF_PATH``` com o path do compilador ESP-IDF.
- Editar o PATH e adicionar o path da toolchain (normalmente /home/user/esp/xtensa-esp32-elf/bin). 
Ou adicionar ```${PATH}``` se a variável do sistema já estiver com a toolchain.
- Em "C/C++ General > Preprocessor Include Paths"
- Clicar na aba "Providers".
- Na lista de Providers selecionar "CDT Cross GCC Built-in Compiler Settings". Mudar o campo "Command to get compiler specs"
para ```xtensa-esp32-elf-gcc ${FLAGS} -E -P -v -dD "${INPUTS}"```.
- Na lista de Providers selecionar "CDT GCC Build Output Parser". Mudar o campo "Compiler command pattern" 
para ```xtensa-esp32-elf-(gcc|g\+\+|c\+\+|cc|cpp|clang)```.
- Em "C/C++ General > Indexer":
- Check "Enable project specific settings".
- Uncheck "Allow heuristic resolution of includes".
