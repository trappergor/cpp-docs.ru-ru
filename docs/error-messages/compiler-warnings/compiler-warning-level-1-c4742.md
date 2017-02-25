---
title: "Предупреждение компилятора (уровень 1) C4742 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4742"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4742"
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4742
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

у 'var' выравнивание отличается в 'file1' и 'file2': число и число  
  
 Выравнивание внешней переменной, для которой задана ссылка или которая определена в двух файлах, отличается от выравнивания, указанного в этих файлах.  Это предупреждение выдается, если компилятор обнаруживает, что `__alignof` для переменной в *file1* отличается от `__alignof` для переменной в *file2*.  Причиной этого может быть использование несовместимых типов при объявлении переменной в разных файлах или использование не совпадающих директив `#pragma pack` в разных файлах.  
  
 Для устранения этого предупреждения следует использовать определение с тем же типом или различные имена переменных.  
  
 Дополнительные сведения см. в разделах [pack](../../preprocessor/pack.md) и [Оператор \_\_alignof](../../cpp/alignof-operator.md).  
  
## Пример  
 Это первый файл, в котором определяется тип.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4742.  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```