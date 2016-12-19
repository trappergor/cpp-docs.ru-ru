---
title: "Использование операторов CArchive &lt;&lt; и &gt;&gt; | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive - класс, операторы"
  - "CArchive - класс, хранение и загрузка объектов"
  - "объекты [C++], загрузка из ранее сохраненных значений"
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование операторов CArchive &lt;&lt; и &gt;&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` предоставляет \<\< и \>\> операторы для записи и чтения простых типов данных, так и `CObject` и наоборот файла.  
  
#### Хранить объект в файле через архив  
  
1.  В следующем примере показано, как сохранить объект в файле через архив:  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### Загрузить объект из значения ранее, хранящихся в файле  
  
1.  В следующем примере показано, как загрузить объект из значения ранее, хранящихся в файле:  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 Как правило, хранить и загрузка данных и наоборот файла с помощью функций `CObject`\- архив в производных классах `Serialize`, необходимо объявлять с макросом **DECLARE\_SERIALIZE**.  Ссылка на объект `CArchive` передается в функцию `Serialize`.  Выполняется вызов функции `IsLoading` объекта `CArchive` для определения называется ли функция `Serialize` для загрузки данных из файла или сохранение в файл.  
  
 Функция `Serialize` сериализуемый `CObject`\- производный класс обычно имеет следующую форму:  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 Шаблон кода с одинаковым как одно AppWizard создает для функции `Serialize` документа \(в классе, производном от **CDocument\)**.  Этот шаблон кода помогает написать код, который легче проверки, поскольку расположении код и код загрузки всегда должны быть параллельны, как показано в следующем примере:  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 Библиотека определяет операторы **\<\<** и **\>\>** для `CArchive` как первый операнд и следующие типы данных и типы класса в качестве второго операнда.  
  
||||  
|-|-|-|  
|`CObject*`|**РАЗМЕР и CSize**|**float**|  
|**WORD**|`CString`|**POINT** и `CPoint`|  
|`DWORD`|**BYTE**|`RECT` и `CRect`.|  
|**Double**|**LONG**|`CTime` и `CTimeSpan`.|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Для сохранения и загрузки `CObject` через архив требуют дополнительного вопроса.  Дополнительные сведения см. в разделе [Храните и загрузки CObjects через архив](../Topic/Storing%20and%20Loading%20CObjects%20via%20an%20Archive.md).  
  
 Операторы **CArchive \<\<** и **\>\>** всегда возвращают ссылку на объект `CArchive`, первый операнд.  Это позволяет включить операторы, как показано ниже:  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## См. также  
 [Сериализация. Сериализация объекта](../Topic/Serialization:%20Serializing%20an%20Object.md)