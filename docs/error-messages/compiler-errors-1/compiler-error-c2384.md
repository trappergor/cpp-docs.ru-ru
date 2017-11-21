---
title: "Ошибка компилятора C2384 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2384
dev_langs: C++
helpviewer_keywords: C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d87769a2e02e6214e474dab2b74859e85a6880b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2384"></a>Ошибка компилятора C2384
member: невозможно применить __declspec(thread) к члену управляемого класса или класса WinRT  
  
 [Поток](../../cpp/thread.md) `__declspec` модификатор не может использоваться на членам управляемого класса или класса среды выполнения Windows.  
  
 Локальное хранилище статического потока в управляемом коде может использоваться только для статически загружаемых библиотек DLL (библиотека загружается статически при запуске процесса). Среда выполнения Windows не поддерживает локальное хранилище потока.  
  
 Следующая строка вызывает ошибку C2384. Также показано, как устранить ее в коде C++/CLI:  
  
```  
// C2384.cpp  
// compile with: /clr /c  
public ref class B {  
public:  
   __declspec( thread ) static int tls_i = 1;   // C2384  
  
   // OK - declare with attribute instead  
   [System::ThreadStaticAttribute]  
   static int tls_j;  
};  
```