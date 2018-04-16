---
title: Предупреждение средств компоновщика LNK4247 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 517605993199942f863faa78e14a022529214a64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4247"></a>Предупреждение средств компоновщика LNK4247
точка входа «декорированное_имя_функции» уже имеет атрибут потока; «атрибут» пропущен  
  
 Точки входа, указанное с [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md), имела потоковый атрибут, но [/CLRTHREADATTRIBUTE (установить атрибут потока среды CLR)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) также был указан с другой потоковой моделью.  
  
 Компоновщик игнорирует значение, указанное в /CLRTHREADATTRIBUTE.  
  
 Чтобы устранить это предупреждение:  
  
-   Удалите /CLRTHREADATTRIBUTE из сборки.  
  
-   Удалите атрибут из файла исходного кода.  
  
-   Удалите атрибут из источника и параметр/CLRTHREADATTRIBUTE из сборки и примите модели потоков CLR по умолчанию.  
  
-   Измените значение, передаваемое /CLRTHREADATTRIBUTE, таким образом, что оно согласуется с атрибутом источника.  
  
-   Измените атрибут в источнике, таким образом, что оно согласуется со значением, передаваемым в /CLRTHREADATTRIBUTE.  
  
 Следующий пример приводит к возникновению ошибки LNK4247  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```