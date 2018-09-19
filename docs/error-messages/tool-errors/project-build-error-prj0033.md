---
title: Ошибка построения проекта PRJ0033 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0033
dev_langs:
- C++
helpviewer_keywords:
- PRJ0033
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c70bd942123c48866c3353443b478de4953668de
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036076"
---
# <a name="project-build-error-prj0033"></a>Ошибка построения проекта PRJ0033

Свойство «Дополнительные зависимости» для настраиваемой сборки шаг для файла «файл» содержало «макрос», что равняется «расширение макроса».

Этап настраиваемого построения на файл содержал ошибку дополнительных зависимостей, возможно, из-за проблемы вычисления макроса. Эта ошибка также может означать, что путь неправильно сформирован, содержащий символы или сочетание символов, которые не разрешены в путь к файлу.

Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Вычисленный путь является абсолютным путем из каталога проекта.