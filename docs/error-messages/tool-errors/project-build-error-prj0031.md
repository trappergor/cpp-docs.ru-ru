---
title: Ошибка построения проекта PRJ0031 | Документы Microsoft
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
ms.openlocfilehash: 4d5ebd25c239a05c4300b574ec0d47035904187d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0031"></a>Ошибка построения проекта PRJ0031
Свойство «Выходные данные» настраиваемого построения шаг для файла «файл» содержало «макрос», что равняется «расширение макроса».  
  
 Этап настраиваемого построения в файле дает некорректный вывод, вероятно, из-за проблемы вычисления макроса. Эта ошибка может также означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути к файлу.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Анализируемый путь является абсолютным путем относительно каталога проекта.