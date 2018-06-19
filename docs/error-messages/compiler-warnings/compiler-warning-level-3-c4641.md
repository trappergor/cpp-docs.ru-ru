---
title: Предупреждение (уровень 3) C4641 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4641
dev_langs:
- C++
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea8413971353e7ffbe6579412d0eed9c735b91b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291441"
---
# <a name="compiler-warning-level-3-c4641"></a>Предупреждение компилятора (уровень 3) C4641
в документирующем комментарии XML присутствует неоднозначная перекрестная ссылка  
  
 Компилятору не удалось однозначно разрешить ссылку. Чтобы устранить это предупреждение, укажите сведения о параметрах, необходимо сделать ссылку однозначной.  
  
 Дополнительные сведения см. в разделе [XML Documentation](../../ide/xml-documentation-visual-cpp.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4641.  
  
```  
// C4641.cpp  
// compile with: /W3 /doc /clr /c  
  
/// <see cref="f" />   // C4641  
// try the following line instead  
// /// <see cref="f(int)" />  
public ref class GR {  
public:  
   void f( int ) {}  
   void f( char ) {}  
};  
```