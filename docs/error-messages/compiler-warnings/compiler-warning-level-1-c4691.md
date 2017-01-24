---
title: "Предупреждение компилятора (уровень 1) C4691 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4691"
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": в неадресуемом объекте "сборка" "файл" ожидался адресуемый тип; вместо этого использован тип, определенный в текущем модуле трансляции  
  
 Отсутствует ссылка на файл метаданных, содержащий определение исходного типа. При компиляции использует определение локального типа.  
  
 В случае, когда необходимо перестроить *file*, можно пропустить предупреждение C4691 или отключить с помощью прагма\-директивы [warning](../../preprocessor/warning.md).  В этом случае выполняется построение файла, в котором компилятор предполагает наличие определения типа, что позволяет пропустить предупреждение C4691.  
  
 Однако если при компиляции используется определение из сборки, не указанной в метаданных, возможно непредвиденное поведение, поскольку в среде CLR типы определяются не только по имени, но и по сборке.  Это означает, что тип Z, содержащийся в библиотеке z.dll, отличается от типа Z из библиотеки y.dll.  
  
## Пример  
 В этом примере представлено определение исходного типа.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## Пример  
 В этом примере содержится ссылка на библиотеку C4691\_a.dll, и объявляется поле типа Original\_Type.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## Пример  
 В следующем примере возникает предупреждение C4691.  Обратите внимание, что в этом примере содержится определение типа Original\_Type, но отсутствует ссылка на библиотеку C4691a.dll.  
  
 Чтобы устранить эту ошибку, используйте ссылку на файл метаданных, в котором содержится определение исходного типа, и удалите локальное объявление и определение.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```