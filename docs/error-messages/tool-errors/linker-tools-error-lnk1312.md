---
title: Ошибка средств компоновщика LNK1312 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 748276ed8fa459c41174f23d32bcef127cbdd510
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300450"
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