---
title: "COleVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "автоматизация, типы параметров"
  - "COleVariant class"
  - "VARIANT data type"
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует тип данных [ВАРИАНТ](http://msdn.microsoft.com/ru-ru/e305240e-9e11-4006-98cc-26f4932d2118).  
  
## Синтаксис  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleVariant::COleVariant](../Topic/COleVariant::COleVariant.md)|Создает объект `COleVariant`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleVariant::Attach](../Topic/COleVariant::Attach.md)|Вложение **VARIANT** к `COleVariant`.|  
|[COleVariant::ChangeType](../Topic/COleVariant::ChangeType.md)|Изменяет другой тип этого объекта `COleVariant`.|  
|[COleVariant::Clear](../Topic/COleVariant::Clear.md)|Очищает объект `COleVariant`.|  
|[COleVariant::Detach](../Topic/COleVariant::Detach.md)|Наконец удаляет **VARIANT** из `COleVariant` и возвращает **VARIANT**.|  
|[COleVariant::GetByteArrayFromVariantArray](../Topic/COleVariant::GetByteArrayFromVariantArray.md)|Извлекает массив байтов из существующего другого массива.|  
|[COleVariant::SetString](../Topic/COleVariant::SetString.md)|Задает строку в указанный тип, обычно ANSI.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleVariant::operator LPCVARIANT](../Topic/COleVariant::operator%20LPCVARIANT.md)|Преобразует значение `COleVariant` в `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](../Topic/COleVariant::operator%20LPVARIANT.md)|Преобразует объект `COleVariant` в `LPVARIANT`.|  
|[COleVariant::operator \=](../Topic/COleVariant::operator%20=.md)|Копирует значение `COleVariant`.|  
|[COleVariant::operator \=\=](../Topic/COleVariant::operator%20==.md)|Сравнивает значения `COleVariant` 2.|  
|[COleVariant::operator \<\<, \>\>](../Topic/COleVariant::operator%20%3C%3C,%20%3E%3E.md)|Выводит значение `COleVariant` к `CArchive` или `CDumpContext` и inputs объект `COleVariant` из `CArchive`.|  
  
## Заметки  
 Этот тип данных используется в ole\-автоматизации.  В частности, структура [DISPPARAMS](http://msdn.microsoft.com/ru-ru/a16e5a21-766e-4287-b039-13429aa78f8b) содержит указатель на массив структур **VARIANT**.  Структура **DISPPARAMS** используется для передачи параметров в [IDispatch::Invoke](http://msdn.microsoft.com/ru-ru/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  Этот класс является производным от структуры **VARIANT**.  Это означает, что можно передать `COleVariant` в параметре который вызывается для **VARIANT** и элементы данных структуры **VARIANT** доступные элементы данных `COleVariant`.  
  
 2 Связанных класса [COleCurrency](../Topic/COleCurrency%20Class.md) и [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) MFC инкапсулируют другие типы данных **CURRENCY** \(`VT_CY`\) и **DATE** \(`VT_DATE`\).  Класс `COleVariant` широко используется в классах DAO; эти классы для конечного см. в разделе использование этого класса, например [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Дополнительные сведения см. в разделе [ВАРИАНТ](http://msdn.microsoft.com/ru-ru/e305240e-9e11-4006-98cc-26f4932d2118), [ВАЛЮТА](http://msdn.microsoft.com/ru-ru/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/ru-ru/a16e5a21-766e-4287-b039-13429aa78f8b) и записи [IDispatch::Invoke](http://msdn.microsoft.com/ru-ru/964ade8e-9d8a-4d32-bd47-aa678912a54d) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о классе `COleVariant` и его использования в ole\-автоматизации см. в разделе "передача параметров в ole\-автоматизации" в статье [автоматизация](../../mfc/automation.md).  
  
## Иерархия наследования  
 `tagVARIANT`  
  
 `COleVariant`  
  
## Требования  
 **Header:**  afxdisp.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)