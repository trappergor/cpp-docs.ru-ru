---
title: Ошибка компилятора C2384 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2384
dev_langs:
- C++
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce139166e2378a26a91bc66db134ec6098aedbdc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33194935"
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