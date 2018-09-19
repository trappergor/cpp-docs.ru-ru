---
title: Ошибка построения проекта PRJ0034 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b271875173bf0e55d94989d60a1c8f7aaf408b2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065586"
---
# <a name="project-build-error-prj0034"></a>Ошибка построения проекта PRJ0034

Свойство «Дополнительные зависимости» для пользовательского уровня проекта сборки содержит шаг «макрос» что равняется «расширение макроса».

Этап настраиваемого построения проекта содержит ошибку в дополнительных зависимостей, возможно, из-за проблемы вычисления макроса. Эта ошибка также может означать, что путь неправильно сформирован, содержащий символы или сочетание символов, которые не разрешены в путь к файлу.

Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Вычисленный путь является абсолютным путем из каталога проекта.