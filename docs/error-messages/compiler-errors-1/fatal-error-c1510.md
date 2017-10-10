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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 373cd74b1649fb9c1bd87cad1903df183f153c0f
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1510"></a>Неустранимая ошибка C1510
Не удается открыть языковой ресурс clui.dll  
  
 Компилятору не удается загрузить DLL языковой ресурс.  
  
Существуют две распространенные причины этой проблемы. При использовании 32-разрядный компилятор и средства, появится это сообщение об ошибке для крупных проектов, использующих более 2 ГБ памяти во время компоновки. Возможное решение на 64-разрядных системах Windows — использовать собственный 64-разрядный или кросс-компилятор и средства для создания кода. Это дает техническое преимущество больше памяти для 64-разрядных приложений. Если необходимо использовать 32-разрядный компилятор, так как выполняются в 32-разрядной системе, в некоторых случаях можно увеличить объем памяти, чтобы компоновщик 3 ГБ. Дополнительные сведения см. в разделе [настройки 4 ГБ: BCDEdit и Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) и [BCDEdit/set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) команды.  

Другой распространенной причиной является установкой Visual Studio прервана или неполна. В этом случае запустите установщик еще раз для восстановления или переустановки Visual Studio.  
  
