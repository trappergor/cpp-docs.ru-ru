---
title: "Компилятора (уровень 1) предупреждение C4650 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: 7
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
ms.openlocfilehash: 449fbd2efd0d6b2b434420996d9175d643f9b7a2
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4650"></a>Предупреждение компилятора (уровень 1) C4650
данные отладки не включены в предкомпилированный заголовок; будут доступны только глобальные символы из заголовка  
  
 Предкомпилированного файла заголовка не был скомпилирован с Microsoft символьной информации для отладки.  
  
 При связывании, полученный исполняемый файл или динамической библиотеки файл не будет содержать отладочную информацию для локальных символов, содержащихся в заголовке.  
  
 Это предупреждение можно избежать посредством перекомпиляции предкомпилированного файла заголовка с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр командной строки.
