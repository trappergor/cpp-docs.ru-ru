---
title: "Предупреждение средств компоновщика LNK4224 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4224"
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение средств компоновщика LNK4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"параметр" больше не поддерживается; не учитывается  
  
 Задан недопустимый устаревший параметр компоновщика. Параметр игнорируется.  
  
 Например, предупреждение LNK4224 может возникать при использовании директивы \/comment в OBJ\-файле.  Для добавления директивы \/comment применяется директива pragma [комментарий](../../preprocessor/comment-c-cpp.md) с нерекомендуемым параметром exestr.  Чтобы просмотреть директивы компоновщика в OBJ\-файле, используйте программу dumpbin с параметром [\/ALL](../../build/reference/all.md).  
  
 По возможности измените файл, исходный для OBJ\-файла, и удалите директиву pragma.  Если пропустить данное предупреждение, возможно возникновение ошибок при выполнении исполняемого файла, скомпилированного с параметром **\/clr:pure**.  
  
## Пример  
 В следующем примере возникает ошибка LNK4224.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```