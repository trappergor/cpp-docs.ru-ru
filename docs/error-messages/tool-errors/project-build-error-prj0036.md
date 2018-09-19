---
title: Ошибка построения проекта PRJ0036 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0036
dev_langs:
- C++
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32b73fb8d86ff537912218ea35089382a93aec4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065196"
---
# <a name="project-build-error-prj0036"></a>Ошибка построения проекта PRJ0036

Свойство «Дополнительные файлы» инструмента веб-развертывания содержало недопустимую запись.

Свойство "Дополнительные файлы" на странице свойств веб-развертывания содержится ошибка, из-за проблемы вычисления макроса. Эта ошибка также может означать, что путь неправильно сформирован, содержащий символы или сочетание символов, которые не разрешены в путь к файлу.

Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Вычисленный путь является абсолютным путем из каталога проекта.

Эта ошибка также может означать, что один из файлов, указанных не существует.