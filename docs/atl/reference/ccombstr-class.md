---
title: "Класс CComBSTR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComBSTR"
  - "CComBSTR"
  - "ATL.CComBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "строки BSTR, программа-оболочка"
  - "CComBSTR"
  - "CComBSTR - класс"
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# Класс CComBSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для `BSTR`.  
  
## Синтаксис  
  
```  
  
class CComBSTR  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComBSTR::CComBSTR](../Topic/CComBSTR::CComBSTR.md)|Конструктор.|  
|[CComBSTR::~CComBSTR](../Topic/CComBSTR::~CComBSTR.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComBSTR::Append](../Topic/CComBSTR::Append.md)|Добавляет строку в `m_str`.|  
|[CComBSTR::AppendBSTR](../Topic/CComBSTR::AppendBSTR.md)|Добавляет `BSTR` к `m_str`.|  
|[CComBSTR::AppendBytes](../Topic/CComBSTR::AppendBytes.md)|Добавляет указанное количество байтов в `m_str`.|  
|[CComBSTR::ArrayToBSTR](../Topic/CComBSTR::ArrayToBSTR.md)|Создает `BSTR` из первого символа каждого элемента в safearray и вложение его к объекту `CComBSTR`.|  
|[CComBSTR::AssignBSTR](../Topic/CComBSTR::AssignBSTR.md)|Присвоит `BSTR` к `m_str`.|  
|[CComBSTR::Attach](../Topic/CComBSTR::Attach.md)|Вложение `BSTR` к объекту `CComBSTR`.|  
|[CComBSTR::BSTRToArray](../Topic/CComBSTR::BSTRToArray.md)|Создает нулевой\- на основе одномерный массив safearray, где каждый элемент массива знаков из объекта `CComBSTR`.|  
|[CComBSTR::ByteLength](../Topic/CComBSTR::ByteLength.md)|Возвращает длину `m_str` в байтах.|  
|[CComBSTR::Copy](../Topic/CComBSTR::Copy.md)|Возвращает копию `m_str`.|  
|[CComBSTR::CopyTo](../Topic/CComBSTR::CopyTo.md)|Возвращает копию `m_str` с помощью параметра **\[out\]**|  
|[CComBSTR::Detach](../Topic/CComBSTR::Detach.md)|Наконец `m_str` удаляет из объекта `CComBSTR`.|  
|[CComBSTR::Empty](../Topic/CComBSTR::Empty.md)|Освобождает `m_str`.|  
|[CComBSTR::Length](../Topic/CComBSTR::Length.md)|Возвращает длину `m_str`.|  
|[CComBSTR::LoadString](../Topic/CComBSTR::LoadString.md)|Загружает ресурс строки.|  
|[CComBSTR::ReadFromStream](../Topic/CComBSTR::ReadFromStream.md)|Загружает объект `BSTR` из потока.|  
|[CComBSTR::ToLower](../Topic/CComBSTR::ToLower.md)|Выполнит преобразование строки в нижний регистр.|  
|[CComBSTR::ToUpper](../Topic/CComBSTR::ToUpper.md)|Преобразует строку в прописными буквами.|  
|[CComBSTR::WriteToStream](../Topic/CComBSTR::WriteToStream.md)|Сохраняет `m_str` в поток.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComBSTR::operator BSTR](../Topic/CComBSTR::operator%20BSTR.md)|Объект `CComBSTR` приводит к `BSTR`.|  
|[CComBSTR::operator \!](../Topic/CComBSTR::operator%20!.md)|Возвращает или `true``false`, в зависимости от того, является ли `m_str``NULL`.|  
|[CComBSTR::operator \!\=](../Topic/CComBSTR::operator%20!=.md)|Сравнивает `CComBSTR` со строкой.|  
|[CComBSTR::operator &](../Topic/CComBSTR::operator%20&.md)|Возвращает адрес `m_str`.|  
|[CComBSTR::operator \+\=](../Topic/CComBSTR::operator%20+=.md)|Добавляет `CComBSTR` к объекту.|  
|[CComBSTR::operator \<](../Topic/CComBSTR::operator%20%3C.md)|Сравнивает `CComBSTR` со строкой.|  
|[CComBSTR::operator \=](../Topic/CComBSTR::operator%20=.md)|Присвоить значение `m_str`.|  
|[CComBSTR::operator \=\=](../Topic/CComBSTR::operator%20==.md)|Сравнивает `CComBSTR` со строкой.|  
|[CComBSTR::operator \>](../Topic/CComBSTR::operator%20%3E.md)|Сравнивает `CComBSTR` со строкой.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComBSTR::m\_str](../Topic/CComBSTR::m_str.md)|Содержит `BSTR`, связанное с объектом `CComBSTR`.|  
  
## Заметки  
 Класс `CComBSTR` программа\-оболочка для `BSTR` s, обладающие префиксом длина\- в строки.  Длина хранится в виде целого числа в области памяти перед данным в строке.  
  
 [BSTR](http://msdn.microsoft.com/ru-ru/1b2d7d2c-47af-4389-a6b6-b01b7e915228) null\- завершено после последнего символа подсчитанный но может также содержать нуль\-символы встроенные в строку.  Длина строки определяется количеством символов, не является первым нуль\-символом.  
  
> [!NOTE]
>  Класс `CComBSTR` предоставляет несколько членов \(конструкторы, операторы присваивания и операторы сравнения\) тех принимает или ANSI или строки в юникоде в виде аргументов.  Версии ANSI этих функций менее эффективны, чем их аналоги в юникоде, так как временные строки в юникоде часто созданы для внутреннего использования.  Для повышения эффективности, используйте версии Юникода, где возможно.  
  
> [!NOTE]
>  Из\-за повышения расширения функциональности поиска, реализованной в Visual Studio .NET, код `bstr = L"String2" + bstr;`, которое может компилироваться в предыдущих выпусках должен быть реализован как вместо `bstr = CStringW(L"String2") + bstr`.  
  
 Список предосторежений при использовании `CComBSTR` см. в разделе [Программирование с использованием CComBSTR](../../atl/programming-with-ccombstr-atl.md).  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [ATL and MFC String Conversion Macros](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)