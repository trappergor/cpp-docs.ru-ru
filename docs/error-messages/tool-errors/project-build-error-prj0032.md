---
title: Ошибка построения проекта PRJ0032 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0032
dev_langs:
- C++
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 106b1c3f470bbdb134a5fd53ebaef65a4392fd4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053580"
---
# <a name="project-build-error-prj0032"></a>Ошибка построения проекта PRJ0032

Свойство «Выходные данные» для этапа настраиваемой сборки уровня проекта содержало «макрос» что равняется «расширение макроса».

Этап настраиваемого построения проекта дает некорректный вывод, вероятно, из-за проблемы вычисления макроса. Эта ошибка также может означать, что путь неправильно сформирован, содержащий символы или сочетание символов, которые не разрешены в путь к файлу.

Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Вычисленный путь является абсолютным путем из каталога проекта.