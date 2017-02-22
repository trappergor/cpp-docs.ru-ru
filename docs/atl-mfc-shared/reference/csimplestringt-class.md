---
title: "CSimpleStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSimpleStringT"
  - "ATL::CSimpleStringT"
  - "ATL::CSimpleStringT<BaseType>"
  - "ATL.CSimpleStringT<BaseType>"
  - "CSimpleStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleStringT class"
  - "shared classes, CSimpleStringT"
  - "строки [C++], ATL - класс"
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSimpleStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет объект `CSimpleStringT`.  
  
## Синтаксис  
  
```  
  
      template <typename   
      BaseType  
      >  
class CSimpleStringT  
```  
  
#### Параметры  
 `BaseType`  
 Тип символа строкового класса.  Может принимать следующие значения:  
  
-   `char` \(для символьных строк ANSI\).  
  
-   `wchar_t` \(для символьных строк в юникоде\).  
  
-   **TCHAR** \(и для символьных строк ANSI и юникод\).  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleStringT::PCXSTR](../Topic/CSimpleStringT::PCXSTR.md)|Указатель на постоянной строки.|  
|[CSimpleStringT::PXSTR](../Topic/CSimpleStringT::PXSTR.md)|Указатель на строку.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleStringT::CSimpleStringT](../Topic/CSimpleStringT::CSimpleStringT.md)|Создает объекты `CSimpleStringT` различными способами.|  
|[CSimpleStringT::~CSimpleStringT](../Topic/CSimpleStringT::~CSimpleStringT.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleStringT::Append](../Topic/CSimpleStringT::Append.md)|Добавляет объект `CSimpleStringT` к существующему объекту `CSimpleStringT`.|  
|[CSimpleStringT::AppendChar](../Topic/CSimpleStringT::AppendChar.md)|Добавляет знак в существующий объект `CSimpleStringT`.|  
|[CSimpleStringT::CopyChars](../Topic/CSimpleStringT::CopyChars.md)|Копирует символ или символы в другую строку.|  
|[CSimpleStringT::CopyCharsOverlapped](../Topic/CSimpleStringT::CopyCharsOverlapped.md)|Копирует символ или символы в другой строке, в которой буферы перекрываются.|  
|[CSimpleStringT::Empty](../Topic/CSimpleStringT::Empty.md)|Принудительно строку, чтобы иметь нулевую длину.|  
|[CSimpleStringT::FreeExtra](../Topic/CSimpleStringT::FreeExtra.md)|Освобождает любую дополнительную память, выделенную ранее строковый объект.|  
|[CSimpleStringT::GetAllocLength](../Topic/CSimpleStringT::GetAllocLength.md)|Получает выбранную длина объекта `CSimpleStringT`.|  
|[CSimpleStringT::GetAt](../Topic/CSimpleStringT::GetAt.md)|Возвращает знак в заданной позиции.|  
|[CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md)|Возвращает указатель на символы в `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md)|Возвращает указатель на символы в `CSimpleStringT`, усечение до заданной длины.|  
|[CSimpleStringT::GetLength](../Topic/CSimpleStringT::GetLength.md)|Возвращает число символов в объекте `CSimpleStringT`.|  
|[CSimpleStringT::GetManager](../Topic/CSimpleStringT::GetManager.md)|Получает диспетчер памяти объекта `CSimpleStringT`.|  
|[CSimpleStringT::GetString](../Topic/CSimpleStringT::GetString.md)|Извлекает строку символов|  
|[CSimpleStringT::IsEmpty](../Topic/CSimpleStringT::IsEmpty.md)|Проверяет, не содержит ли объект `CSimpleStringT` никакие символы.|  
|[CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md)|Запрещает ссылка учитываются и защищает строка в буфере.|  
|[CSimpleStringT::Preallocate](../Topic/CSimpleStringT::Preallocate.md)|Выделяет определенное количество памяти для буфера знаков.|  
|[CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)|Управление выпусков буфера, возвращенных `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](../Topic/CSimpleStringT::ReleaseBufferSetLength.md)|Управление выпусков буфера, возвращенных `GetBuffer`.|  
|[CSimpleStringT::SetAt](../Topic/CSimpleStringT::SetAt.md)|Задает знак в заданной позиции.|  
|[CSimpleStringT::SetManager](../Topic/CSimpleStringT::SetManager.md)|Задает диспетчер памяти объекта `CSimpleStringT`.|  
|[CSimpleStringT::SetString](../Topic/CSimpleStringT::SetString.md)|Задает строку объекта `CSimpleStringT`.|  
|[CSimpleStringT::StringLength](../Topic/CSimpleStringT::StringLength.md)|Возвращает число символов в указанной строке.|  
|[CSimpleStringT::Truncate](../Topic/CSimpleStringT::Truncate.md)|Усекает строки до заданной длины.|  
|[CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md)|Включает ссылку учитываются и освобождает строка в буфере.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md)|Напрямую обращается к символы, хранящиеся в объекте `CSimpleStringT` c. вставка строки как стили.|  
|[CSimpleStringT::operator](../Topic/CSimpleStringT::operator.md)|Возвращает знак в заданной позиции — подстановка оператора для `GetAt`.|  
|[CSimpleStringT::operator \+\=](../Topic/CSimpleStringT::operator%20+=.md)|Сцепляет новую строку в конец существующей строки.|  
|[CSimpleStringT::operator \=](../Topic/CSimpleStringT::operator%20=.md)|Присвоить новое значение объекта `CSimpleStringT`.|  
  
## Заметки  
 `CSimpleStringT` базовый класс для различных классов строки, поддерживаемых Visual C\+\+.  Он предоставляет минимальную поддержку управления памятью объект строки и основной манипуляции буфера.  Для более сложных объектов строки см. в разделе [класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md).  
  
## Требования  
 **Header:** atlsimpstr.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)