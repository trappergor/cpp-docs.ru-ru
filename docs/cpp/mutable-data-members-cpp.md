---
title: "Изменяемые члены данных (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "mutable_cpp"
  - "mutable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mutable - ключевое слово [C++]"
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Изменяемые члены данных (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это ключевое слово может применяться только к данным\-членам класса, которые не являются статическими или константами.  Если данные\-член объявлены как `mutable`, им можно присваивать значения из функции\-члена со спецификатором **const**.  
  
## Синтаксис  
  
```  
  
mutable member-variable-declaration;  
```  
  
## Заметки  
 Например, следующий код компилируется без ошибок, поскольку член `m_accessCount` объявлен как `mutable`, и поэтому может изменяться функцией `GetFlag`, хотя функция `GetFlag` объявлена как постоянная функция\-член.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)