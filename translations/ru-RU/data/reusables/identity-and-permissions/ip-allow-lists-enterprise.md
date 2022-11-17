---
ms.openlocfilehash: 5c02cf240a1d23e9549a534381d9914bd8dc0ebd
ms.sourcegitcommit: fb047f9450b41b24afc43d9512a5db2a2b750a2a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2022
ms.locfileid: "145110008"
---
При включении списка разрешений настроенные IP-адреса сразу добавляются в списки разрешений организаций в пределах вашего предприятия. Если отключить список разрешений, адреса будут удалены из списков разрешений организации.

Вы можете автоматически добавить в список разрешений любые IP-адреса, настроенные для {% data variables.product.prodname_github_apps %}, установленных на предприятии. Создатель {% data variables.product.prodname_github_app %} настроил список разрешений для приложения, указывающий IP-адреса, с использованием которых выполняется приложение. Наследуя их список разрешений в вашей среде, вы избегаете отправки запросов на подключение от отклоняемого приложения. Дополнительные сведения см. в разделе [Разрешение доступа к приложениям GitHub](#allowing-access-by-github-apps).