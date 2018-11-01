---
title: Ошибка построения проекта PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 2a6cde4ca48acb9aadfe3109084483dbb554e1e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488079"
---
# <a name="project-build-error-prj0030"></a>Ошибка построения проекта PRJ0030

Ошибка расширения макроса. Оцените рекурсии превышает 32 уровней для $(макрос).

Эта ошибка вызвана рекурсии в макросе. Например, если задать **промежуточный каталог** свойство (см. в разделе [свойств "Общие" (проект)](../../ide/general-property-page-project.md)) $ (IntDir), будет иметь рекурсии.

Чтобы устранить эту ошибку, не следует определять макросы или свойства с помощью макросов, они используются для определения.