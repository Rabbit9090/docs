---
title: Включение ведения журналов отладки
shortTitle: Enable debug logging
intro: 'Если журналы рабочих процессов не предоставляют достаточно сведений для диагностики причин несоответствующего выполнения рабочего процесса, задания или шага, можно дополнительно включить ведение журнала отладки.'
redirect_from:
  - /actions/managing-workflow-runs/enabling-debug-logging
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
ms.openlocfilehash: 4d991aa5166c57aec47f98a59b41b78ece5b7254
ms.sourcegitcommit: 7b86410fc3bc9fecf0cb71dda4c7d2f0da745b85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2022
ms.locfileid: '148009984'
---
{% data reusables.actions.enterprise-beta %} {% data reusables.actions.enterprise-github-hosted-runners %}

Эти дополнительные журналы включаются путем настройки секретов в репозитории, содержащем рабочий процесс, поэтому будут применяться те же требования к разрешениям:

- {% data reusables.actions.permissions-statement-secrets-repository %}
- {% data reusables.actions.permissions-statement-secrets-environment %}
- {% data reusables.actions.permissions-statement-secrets-organization %}
- {% data reusables.actions.permissions-statement-secrets-api %}

Дополнительные сведения о настройке секретов см. в разделе [Создание и использование зашифрованных секретов](/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets).

{% ifversion debug-reruns %}

Кроме того, любой пользователь, имеющий доступ к запуску рабочего процесса, может включить ведение журнала диагностики средства выполнения тестов и ведение журнала пошаговой отладки для повторного запуска рабочего процесса. Дополнительные сведения см. в статье [Повторный запуск рабочих процессов и заданий](/actions/managing-workflow-runs/re-running-workflows-and-jobs).

 {% endif %}

## Включение ведения журнала диагностики средства выполнения

Ведение журнала диагностики средства выполнения предоставляет дополнительные файлы журнала, содержащие сведения о том, как средство выполнения выполняет задание. В архив журнала добавляются два дополнительных файла журнала:

* Журнал процессов средства выполнения, который содержит сведения о координации и настройке средства для выполнения заданий.
* Журнал рабочих процессов, который регистрирует выполнение задания.

1. Чтобы включить ведение журнала диагностики средства выполнения, задайте секрету `ACTIONS_RUNNER_DEBUG` в репозитории, содержащем рабочий процесс, значение `true`.

1. Чтобы скачать журналы диагностики средства выполнения, скачайте архив журналов выполнения рабочего процесса. Журналы диагностики средства выполнения содержатся в папке `runner-diagnostic-logs`. Дополнительные сведения о скачивании журналов см. в разделе [Скачивание журналов](/actions/managing-workflow-runs/using-workflow-run-logs/#downloading-logs).

## Включение ведения журнала отладки шагов

Ведение журнала отладки шагов повышает уровень детализации журналов задания во время и после выполнения задания.

1. Чтобы включить ведение журнала отладки шагов, задайте для секрета `ACTIONS_STEP_DEBUG` в репозитории, содержащем рабочий процесс, значение `true`.

1. После настройки секрета в журналах шагов отображаются дополнительные события отладки. Дополнительные сведения см. в разделе [Просмотр журналов для диагностики сбоев](/actions/managing-workflow-runs/using-workflow-run-logs/#viewing-logs-to-diagnose-failures).