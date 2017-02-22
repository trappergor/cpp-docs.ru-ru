---
title: "CComCurrency Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComCurrency"
  - "ATL.CComCurrency"
  - "ATL::CComCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCurrency class"
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComCurrency` содержит методы и операторы для создания объекта CURRENCY и управления им.  
  
## Синтаксис  
  
```  
  
class CComCurrency  
  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCurrency::CComCurrency](../Topic/CComCurrency::CComCurrency.md)|Конструктор объекта `CComCurrency`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCurrency::GetCurrencyPtr](../Topic/CComCurrency::GetCurrencyPtr.md)|Возвращает адрес элемента данных `m_currency`.|  
|[CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md)|Вызовите этот метод для возврата дробной части объекта `CComCurrency`.|  
|[CComCurrency::GetInteger](../Topic/CComCurrency::GetInteger.md)|Вызовите этот метод для возврата целой части объекта `CComCurrency`.|  
|[CComCurrency::Round](../Topic/CComCurrency::Round.md)|Вызовите этот метод для округления объекта `CComCurrency` до ближайшего целого значения.|  
|[CComCurrency::SetFraction](../Topic/CComCurrency::SetFraction.md)|Вызовите этот метод для установки дробной части объекта `CComCurrency`.|  
|[CComCurrency::SetInteger](../Topic/CComCurrency::SetInteger.md)|Вызовите этот метод для установки целой части объекта `CComCurrency`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCurrency::operator \-](../Topic/CComCurrency::operator%20-2.md)|Этот оператор используется для вычитания объекта `CComCurrency`.|  
|[CComCurrency::operator \!\=](../Topic/CComCurrency::operator%20!=.md)|Проверяет неравенство двух объектов `CComCurrency`.|  
|[CComCurrency::operator \*](../Topic/CComCurrency::operator%20*.md)|Этот оператор используется для умножения объекта `CComCurrency`.|  
|[CComCurrency::operator \*\=](../Topic/CComCurrency::operator%20*=.md)|Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator \/](../Topic/CComCurrency::operator%20-1.md)|Этот оператор используется для деления объекта `CComCurrency`.|  
|[CComCurrency::operator \/\=](../Topic/CComCurrency::operator%20-=2.md)|Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator \+](../Topic/CComCurrency::operator%20+.md)|Этот оператор используется для сложения объекта `CComCurrency`.|  
|[CComCurrency::operator \+\=](../Topic/CComCurrency::operator%20+=.md)|Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator \<](../Topic/CComCurrency::operator%20%3C.md)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.|  
|[CComCurrency::operator \<\=](../Topic/CComCurrency::operator%20%3C=.md)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.|  
|[CComCurrency::operator \=](../Topic/CComCurrency::operator%20=.md)|Этот оператор присваивает объекту `CComCurrency` новое значение.|  
|[CComCurrency::operator \-\=](../Topic/CComCurrency::operator%20-=1.md)|Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator \=\=](../Topic/CComCurrency::operator%20==.md)|Этот оператор сравнивает два объекта `CComCurrency` на равенство.|  
|[CComCurrency::operator \>](../Topic/CComCurrency::operator%20%3E.md)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.|  
|[CComCurrency::operator \>\=](../Topic/CComCurrency::operator%20%3E=.md)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.|  
|[CComCurrency::operator CURRENCY](../Topic/CComCurrency::operator%20CURRENCY.md)|Приведение объекта `CURRENCY`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCurrency::m\_currency](../Topic/CComCurrency::m_currency.md)|Переменная `CURRENCY`, созданная экземпляром класса.|  
  
## Заметки  
 `CComCurrency` — это оболочка для типа данных **CURRENCY**.  **CURRENCY** реализуется как целое 8\-байтное значение в дополнительном коде, умноженное на 10 000.  Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее.  Тип данных**CURRENCY** крайне полезен для денежных расчетов или расчетов с фиксированной запятой, когда важна точность.  
  
 Оболочка **CComCurrency**  реализует арифметические операции, операции присваивания и сравнения для этого типа с фиксированной запятой.  Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.  
  
 Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой.  Дробная часть хранится в системе как целое значение от —9 999 \(**CY\_MIN\_FRACTION**\) до \+9 999 \(**CY\_MAX\_FRACTION**\).  Метод [CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md) возвращает значение, умноженное на 10 000 \(**CY\_SCALE**\).  
  
 При указании целого и дробного компонента объекта **CComCurrency**  следует помнить, что дробная часть — это число в диапазоне от 0 до 9 999.  Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой.  Хотя две последние цифры не отображаются, их необходимо учитывать.  
  
|Значение|Возможные значения CComCurrency|  
|--------------|-------------------------------------|  
|$10.50|CComCurrency\(10,5000\) *или* CComCurrency\(10.50\)|  
|$10.05|CComCurrency\(10,500\) *или* CComCurrency\(10.05\)|  
  
 Значения **CY\_MIN\_FRACTION**, **CY\_MAX\_FRACTION** и  **CY\_SCALE** определены в файле atlcur.h.  
  
## Требования  
 **Заголовок:** atlcur.h  
  
## См. также  
 [COleCurrency Class](../Topic/COleCurrency%20Class.md)   
 [CURRENCY](http://msdn.microsoft.com/ru-ru/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Class Overview](../../atl/atl-class-overview.md)