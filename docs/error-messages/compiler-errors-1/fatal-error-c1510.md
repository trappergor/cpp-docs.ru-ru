---
title: "Неустранимая ошибка C1510 | Документы Microsoft"
ms.custom: 
ms.date: 04/11/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1510
dev_langs:
- C++
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
caps.latest.revision: 1
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 05aee6ce5cba18d0517a134eb217a149098beb6e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1510"></a>Неустранимая ошибка C1510
Не удается открыть языковой ресурс clui.dll  
  
 Компилятору не удается загрузить DLL языковой ресурс.  
  
Существуют две распространенные причины этой проблемы. При использовании 32-разрядный компилятор и средства, появится это сообщение об ошибке для крупных проектов, использующих более 2 ГБ памяти во время компоновки. Возможное решение на 64-разрядных системах Windows — использовать собственный 64-разрядный или кросс-компилятор и средства для создания кода. Это дает техническое преимущество больше памяти для 64-разрядных приложений. Если необходимо использовать 32-разрядный компилятор, так как выполняются в 32-разрядной системе, в некоторых случаях можно увеличить объем памяти, чтобы компоновщик 3 ГБ. Дополнительные сведения см. в разделе [настройки 4 ГБ: BCDEdit и Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) и [BCDEdit/set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) команды.  

Другой распространенной причиной является установкой Visual Studio прервана или неполна. В этом случае запустите установщик еще раз для восстановления или переустановки Visual Studio.  
  
