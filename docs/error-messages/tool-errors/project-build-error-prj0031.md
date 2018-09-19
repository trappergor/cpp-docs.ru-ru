---
title: Ошибка построения проекта PRJ0031 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0031
dev_langs:
- C++
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce97e8f540295f5a2968fce22312b8e0e34cfd2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076896"
---
# <a name="project-build-error-prj0031"></a>Ошибка построения проекта PRJ0031

Свойство «Выходные данные» для настраиваемой сборки шаг для файла «файл» содержало «макрос», что равняется «расширение макроса».

Настраиваемый этап построения с файлом дает некорректный вывод, вероятно, из-за проблемы вычисления макроса. Эта ошибка также может означать, что путь неправильно сформирован, содержащий символы или сочетание символов, которые не разрешены в путь к файлу.

Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Вычисленный путь является абсолютным путем из каталога проекта.