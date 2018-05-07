---
title: Предупреждение средств компоновщика LNK4247 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6096bbfba9c60d8ed28aa660d078cd155f0316a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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