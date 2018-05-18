---
title: Ошибка построения проекта PRJ0034 | Документы Microsoft
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
ms.openlocfilehash: a65ca2c53ba2801f861471c66f7e1f2ec8766345
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0034"></a>Ошибка построения проекта PRJ0034
Свойство «Дополнительные зависимости» для пользовательского уровня проекта построения содержится шаг «макрос» что равняется «расширение макроса».  
  
 Этап настраиваемого построения проекта содержит ошибку в дополнительных зависимостей, возможно, из-за проблемы вычисления макроса. Эта ошибка может также означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути к файлу.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Анализируемый путь является абсолютным путем относительно каталога проекта.