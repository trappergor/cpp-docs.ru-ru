---
title: "Класс codecvt_base | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "codecvt_base"
  - "xlocale/std::codecvt_base"
  - "std.codecvt_base"
  - "std::codecvt_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_base - класс"
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 21
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс codecvt_base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Базовый класс для класса codecvt, используемый для определения тип перечисления с именем **result**, используется в качестве типа возвращаемого значения для функций\-членов аспекта, чтобы показать результат преобразования.  
  
## Синтаксис  
  
```  
class codecvt_base : public locale::facet {  
public:  
    enum result {ok, partial, error, noconv};  
    codecvt_base(  
        size_t _Refs = 0  
);  
    bool always_noconv() const;  
    int max_length() const;  
    int encoding() const;  
    ~codecvt_base()  
protected:  
    virtual bool do_always_noconv() const;  
    virtual int do_max_length() const;  
    virtual int do_encoding() const;  
};  
```  
  
## Заметки  
 Класс описывает перечисление являются одинаковыми для всех специализациям класса шаблона [codecvt](../standard-library/codecvt-class.md).  Результат перечисления описаны возможные возвращаемые значения из [do\_in](../Topic/codecvt::do_in.md) или [do\_out](../Topic/codecvt::do_out.md).  
  
-   **ОК**, если преобразование между внутренними и внешними кодированиями символа завершается успешно.  
  
-   **partial**, если назначение для преобразования не достаточно большое, чтобы успешно.  
  
-   **ошибка**, если последовательность источника сформированный больноой.  
  
-   если функция **noconv** не выполняет преобразование.  
  
## Требования  
 **Header:**\<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)