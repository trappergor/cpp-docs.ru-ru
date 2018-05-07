---
title: Ошибка построения проекта PRJ0032 | Документы Microsoft
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
ms.openlocfilehash: d6be9a343ae9d9ce1e3d862cc0a397f1d61ccdea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0032"></a>Ошибка построения проекта PRJ0032
Свойство «Выходные данные» для этапа настраиваемого построения уровня проекта содержало «макрос» что равняется «расширение макроса».  
  
 Этап настраиваемого построения проекта дает некорректный вывод, вероятно, из-за проблемы вычисления макроса. Эта ошибка может также означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути к файлу.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Анализируемый путь является абсолютным путем относительно каталога проекта.