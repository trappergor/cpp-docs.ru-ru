---
title: "Ошибка построения проекта PRJ0034 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0034
dev_langs: C++
helpviewer_keywords: PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e68097d234519cdea75875d355ef798672ad4b22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0034"></a>Ошибка построения проекта PRJ0034
Свойство «Дополнительные зависимости» для пользовательского уровня проекта построения содержится шаг «макрос» что равняется «расширение макроса».  
  
 Этап настраиваемого построения проекта содержит ошибку в дополнительных зависимостей, возможно, из-за проблемы вычисления макроса. Эта ошибка может также означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути к файлу.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Анализируемый путь является абсолютным путем относительно каталога проекта.