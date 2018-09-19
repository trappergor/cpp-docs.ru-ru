---
title: Ошибка построения проекта PRJ0030 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 964fedd40f577a8b337c4ad0c20ba80d33ed2a23
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099926"
---
# <a name="project-build-error-prj0030"></a>Ошибка построения проекта PRJ0030

Ошибка расширения макроса. Оцените рекурсии превышает 32 уровней для $(макрос).

Эта ошибка вызвана рекурсии в макросе. Например, если задать **промежуточный каталог** свойство (см. в разделе [свойств "Общие" (проект)](../../ide/general-property-page-project.md)) $ (IntDir), будет иметь рекурсии.

Чтобы устранить эту ошибку, не следует определять макросы или свойства с помощью макросов, они используются для определения.