---
title: "Ошибка построения проекта PRJ0034 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0c4b9e5fc6c2b80729df021f439f537d60b34501
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="project-build-error-prj0034"></a>Ошибка построения проекта PRJ0034
Свойство «Дополнительные зависимости» для пользовательского уровня проекта построения содержится шаг «макрос» равен «расширение макроса».  
  
 Этап настраиваемого построения проекта содержит ошибку в дополнительной зависимости, вероятно, из-за проблемы вычисления макроса. Эта ошибка также может означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути к файлу.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути. Анализируемый путь является абсолютным путем относительно каталога проекта.
