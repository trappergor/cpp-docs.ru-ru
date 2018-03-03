---
title: "Блоки | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function definitions, blocks in code
- blocks
- compound statements
- statements, compound
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60126db8e2a8f7fe9e56041c4f5b119df828958c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="blocks"></a>Blocks
Последовательность объявлений, определений и операторов, заключенная в фигурные скобки (**{ }**), называется "блоком". Существует два типа блоков в С. «Составной оператор» оператор, состоящие из одной или нескольких инструкций (см. [составной оператор](../c-language/compound-statement-c.md)), один тип блока. Второй тип блоков — определение функции — состоит из составного оператора (тело функции) и связанного заголовка функции (имя функции, тип возвращаемого значения и формальные параметры). Блок, находящийся в другом блоке, называется вложенным.  
  
 Обратите внимание, что хотя все составные операторы заключены в фигурные скобки, не все элементы, заключенные в фигурные скобки, являются составным оператором. Например, несмотря на то что спецификации элементов массива, структуры или перечисления могут быть заключены в фигурные скобки, они не являются составными операторами.  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)