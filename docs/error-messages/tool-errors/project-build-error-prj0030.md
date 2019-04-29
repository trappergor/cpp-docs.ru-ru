---
title: Ошибка построения проекта PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: aa1c8539247287f7644742857c3cb7de321a20a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385411"
---
# <a name="project-build-error-prj0030"></a>Ошибка построения проекта PRJ0030

Ошибка расширения макроса. Оцените рекурсии превышает 32 уровней для $(макрос).

Эта ошибка вызвана рекурсии в макросе. Например, если задать **промежуточный каталог** свойство (см. в разделе [свойств "Общие" (проект)](../../build/reference/general-property-page-project.md)) $ (IntDir), будет иметь рекурсии.

Чтобы устранить эту ошибку, не следует определять макросы или свойства с помощью макросов, они используются для определения.