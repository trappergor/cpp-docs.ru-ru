---
title: "Ошибка средств компоновщика LNK1312 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1312
dev_langs: C++
helpviewer_keywords: LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d7f7b57512f58402403a50bf57176f975769573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1312"></a>Ошибка средств компоновщика LNK1312
Недопустимый или поврежденный файл: не удается импортировать сборку  
  
 При построении сборки файл, отличный от модуля или сборки, скомпилированной с **/CLR** передан **/ASSEMBLYMODULE** компоновщика.  При передаче в объектный файл для **/ASSEMBLYMODULE**, просто передать объект непосредственно компоновщику вместо **/ASSEMBLYMODULE**.  
  
## <a name="example"></a>Пример  
 Следующий пример создан OBJ-файле.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK1312.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```