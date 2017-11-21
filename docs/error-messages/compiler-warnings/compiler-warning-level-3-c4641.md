---
title: "Предупреждение (уровень 3) C4641 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4641
dev_langs: C++
helpviewer_keywords: C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a25a131efd61da971e973fda3364970ec7a32619
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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