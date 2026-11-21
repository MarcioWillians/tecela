# Tecelã — Fio a fio, tecendo as linhas da vida escolar

Versão 1.11.1 · Autor e idealizador: Márcio Willians Barreto de Andrade · marciowillians@gmail.com
Software livre: GNU GPL versão 3, com termos adicionais (arquivo `LICENSE`). Toda cópia deve manter visível o aviso “Tecelã — criada por Márcio Willians Barreto de Andrade”, e versões modificadas devem se identificar como diferentes da original e informar que o autor original não tem responsabilidade sobre as alterações. Bibliotecas e fontes: veja no app, em Ajuda → Créditos e licenças.

A Tecelã é um app em um único arquivo HTML, offline, para a professora ou o professor de classe Waldorf registrar anotações, observações do período, atas, vivências, perfis, o conselho de classe, o planejamento e o acompanhamento das crianças e das famílias, e tecer com esses fios o Boletim Descritivo de cada criança.

## Baixar e atualizar

A versão mais recente fica em <https://github.com/MarcioWillians/tecela/releases/latest>. Para atualizar: salve o seu arquivo (💾 Salvar), baixe o novo `Tecela.html` e substitua o antigo na mesma pasta, com o mesmo nome. Sugestões, problemas e pedidos: marciowillians@gmail.com. Não envie dados de crianças, seus ou da entidade, nem prints com nomes.

## Como usar

1. Abra `dist/Tecela.html` com dois cliques, em qualquer navegador atual. Funciona sem internet.
2. Na tela inicial, escolha: Continuar, Abrir um arquivo da Tecelã (`.tecela`), Novo, Novo a partir de boletins anteriores (`.docx`), Modelo de demonstração ou Computador de terceiros.
3. O que você digita é gravado sozinho neste navegador; use **💾 Salvar** (Ctrl+S) com frequência para gravar tudo no seu arquivo `.tecela`, a cópia que vale. De tempos em tempos (a Tecelã lembra a cada 5 dias), faça também a **🛟 cópia de segurança**, sempre com senha, e guarde-a fora do computador: pendrive, Google Drive, OneDrive ou o seu e-mail.
4. No celular Android, abra a Tecelã pelo endereço <https://marciowillians.github.io/tecela/Tecela.html>: aberto pelo gerenciador de arquivos (`content://`), o navegador não entrega à página o arquivo `.tecela` escolhido. No celular, o “Salvar” baixa uma cópia nova do arquivo.
5. Mantenha o `Tecela.html` sempre no mesmo lugar: o navegador associa os dados ao local do arquivo.

Para trocar material com colegas, use **Ajustes e arquivo → Partilha pedagógica**: o arquivo `.tecela-partilha` leva só planejamentos, repertório, modelos, comunicados, vivências e festas, sem dados de crianças, famílias, professoras ou da escola, e só acrescenta itens em quem recebe.

Fotos e documentos escaneados (a ata assinada, a caderneta, bilhetes) ficam em **A turma → Digitalizados**, em álbuns, ligados à criança, à ata, à vivência ou à reunião; as fotos são reduzidas sozinhas e o PDF vai até 3 MB. São, de longe, o que mais ocupa espaço no arquivo: a Tecelã mostra o peso ao incluir e em Ajustes → Armazenamento. Eles nunca entram na partilha.

O manual completo está dentro do app, em Ajuda.

## O que tem aqui

| Caminho | Conteúdo |
|---|---|
| `dist/Tecela.html` | O aplicativo completo, num único arquivo |
| `src/` | Código-fonte (HTML, CSS e JavaScript separados) |
| `vendor/` | Biblioteca docx 9.7.1 (MIT) e sua licença |
| `assets/` | Logotipos, ícone, prancha da identidade visual e os scripts que os geram |
| `ferramentas/` | Scripts que extraem as habilidades da BNCC e da Computação dos PDFs oficiais e o conteúdo programático de referência |
| `testes/` | Testes automáticos com Playwright |
| `build.py` | Monta `dist/Tecela.html` a partir de `src/` |
| `continuar.md` | Para quem vai mexer no código: regras, mapa do código e histórico de versões |
| `Tecelã — Especificação do projeto.docx` | Para quem quer entender o produto: decisões, módulos, dados, identidade visual e créditos |

## Para alterar

1. Edite os arquivos em `src/`.
2. Rode `python3 build.py`.
3. Rode os testes (precisam do Playwright), por exemplo `LOG=log.txt node testes/teste-v111.js`:
   - `teste-demo.js`: percorre o modelo e gera DOCX e PDF;
   - `teste-fluxo.js`: primeiro uso, senha, arquivo, virada do ano;
   - `teste-varredura.js`: todas as telas no computador, no celular e no tablet com tema escuro;
   - `teste-partilha.js`: Partilha pedagógica (inclusive a classificação obrigatória de toda coleção e campo);
   - `teste-novidades.js` e `teste-v12.js` a `teste-v111.js`: as funções de cada versão (no `teste-v12`, `DOCX=pasta` com boletins **fictícios** testa o importador). O `teste-v111.js` cobre a cópia de segurança com senha e o lembrete, o desfazer nos textos e os digitalizados.
4. Antes de entregar, rode todos e confira que nenhum aponta erro.
