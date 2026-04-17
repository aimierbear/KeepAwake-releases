# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt-BR.md) · [Italiano](README.it.md)**

Um app para a barra de menus do macOS que controla o comportamento de suspensão do MacBook com dois interruptores independentes — mantém seu Mac acordado com a tampa fechada e bloqueia a suspensão por inatividade enquanto você trabalha.

> 📦 **Este repositório distribui apenas o `.dmg` assinado e notarizado. O código-fonte está em um repositório privado.**

## ⬇️ Download

Última versão → **[KeepAwake-releases/releases/latest](../../releases/latest)**

Cada `.dmg` é assinado com o Developer ID `C3SNXE45AV (Xiaoneng Wu)` e notarizado pela Apple. O Gatekeeper do macOS aceita sem o segundo diálogo de confirmação "baixado da internet".

## 🧰 Requisitos do sistema

- macOS 14 Sonoma ou superior
- Apple Silicon ou Intel

## ✨ Recursos

- **Acordado com tampa fechada** — mantém o Mac funcionando mesmo com a tampa fechada (autorização de administrador necessária na primeira vez)
- **Impedir suspensão por inatividade** — suprime a suspensão por inatividade enquanto o KeepAwake está em execução (IOKit assertion)
- **Temporizador de desligamento automático** — 30 min / 1 / 2 / 4 / 8 horas
- **Início automático no login, lembrar último estado, redefinir interruptores ao sair**
- **Resiliente a falhas** — se o app travar, o helper redefine `disablesleep` para 0 após 60 s
- **15 idiomas** — segue o idioma do sistema macOS

## 📥 Instalação

1. Baixe `KeepAwake-0.3.0.dmg` a partir da [última versão](../../releases/latest)
2. Clique duas vezes no DMG para montar, arraste **KeepAwake.app** para `/Applications`
3. Inicie pelo Launchpad ou Aplicativos
4. Na primeira vez que ativar "Acordado com tampa fechada", o macOS pedirá permissão para adicionar um item em segundo plano → clique em **Permitir**

## 🔐 Assinatura e notarização

- Developer ID: `Xiaoneng Wu (C3SNXE45AV)`
- Serviço de Notarização Apple: ✅ Aceito
- Ticket grampeado (funciona offline, o Gatekeeper pode verificar sem rede)

## ⚠️ Risco de superaquecimento com tampa fechada — por favor, leia

**A principal saída de ar do MacBook fica sob o teclado.** Quando a tampa está fechada e o laptop está apoiado sobre uma superfície plana, o fluxo de ar fica restrito. Executar cargas pesadas nesse estado (exportação de vídeo, compilação, treinamento de ML, inferência de IA prolongada, jogos) pode causar:

- Thermal throttling de CPU/GPU → sua tarefa na verdade fica *mais lenta*
- Envelhecimento acelerado da bateria por temperaturas altas prolongadas
- Em casos extremos, desligamento térmico ou dano ao hardware

**Uso seguro:**

- ✅ Adequado para tarefas **leves** em segundo plano — sincronização de arquivos, downloads, manter SSH / desktop remoto, recepção AirPlay
- ⚠️ Para cargas **pesadas** com tampa fechada, eleve o laptop ou use uma base refrigerada. **Nunca** coloque em cama, cobertor, sofá, ou dentro de uma mochila.
- ❌ Não combine "tampa fechada + carga pesada + ventilação bloqueada"

`Impedir suspensão por inatividade` também substitui a economia de bateria. Ligue quando precisar, desligue quando não precisar mais.

**KeepAwake não monitora temperatura ou carga. O gerenciamento de risco é sua responsabilidade.**

### 🌡️ Novidade v0.3: Proteção térmica passiva (ativada por padrão)

Enquanto "Acordado com tampa fechada" está ativo, o KeepAwake monitora o estado térmico do sistema (`NSProcessInfo.thermalState`):

- `Serious` por 60 s → desliga automaticamente "Acordado com tampa fechada" para que o sistema possa suspender e esfriar
- `Critical` → desliga imediatamente

Quando acionado, uma notificação é exibida e um banner de alerta aparece no topo do menu. Você pode desativar nas preferências do menu ("Proteção térmica com tampa fechada"), mas **não é recomendado**.

**Lembrete: a proteção passiva por software não substitui o resfriamento físico.** Continue evitando "tampa fechada + carga pesada + ventilação bloqueada".

## 🔒 Sobre o código-fonte

O repositório de código é privado. Este repositório existe apenas para distribuir o DMG assinado e notarizado. Se você precisar de acesso ao código para auditoria ou contribuição, entre em contato com o autor.

## Licença

Uso pessoal.
