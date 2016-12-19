---
title: "CMetaFileDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMetaFileDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMetaFileDC class"
  - "метафайлы, реализация"
  - "Windows metafiles [C++]"
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMetaFileDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует метафайл Windows, который содержит последовательность приборный интерфейс графических устройств \(GDI\) управляет что можно воспроизводить, чтобы создать желаемый способ или отправлять СМС.  
  
## Синтаксис  
  
```  
class CMetaFileDC : public CDC  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMetaFileDC::CMetaFileDC](../Topic/CMetaFileDC::CMetaFileDC.md)|Создает объект `CMetaFileDC`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMetaFileDC::Close](../Topic/CMetaFileDC::Close.md)|Закрывает контекст устройства и создает дескриптор метафайла.|  
|[CMetaFileDC::CloseEnhanced](../Topic/CMetaFileDC::CloseEnhanced.md)|Закрывает контекст устройства улучшенный\- метафайла и создает дескриптор улучшенный\- метафайла.|  
|[CMetaFileDC::Create](../Topic/CMetaFileDC::Create.md)|Создает контекст устройства метафайла Windows и вложение его к объекту `CMetaFileDC`.|  
|[CMetaFileDC::CreateEnhanced](../Topic/CMetaFileDC::CreateEnhanced.md)|Создает контекст устройства улучшенный\- формата метафайла для метафайла.|  
  
## Заметки  
 Для реализации метафайл Windows, сначала создайте объект `CMetaFileDC`.  Вызовите конструктор `CMetaFileDC`, затем вызовите функцию\-член [Создание](../Topic/CMetaFileDC::Create.md), который создает контекст устройства метафайла Windows и вложение его к объекту `CMetaFileDC`.  
  
 Затем отправьте объект `CMetaFileDC` последовательность GDI `CDC` управляет что необходимо для его воспроизведения.  Только эти команды GDI, которые создают вывод, например `MoveTo` и `LineTo`, можно использовать.  
  
 После того как нужные команды, отправляемые к метафайлу, вызовите функцию\-член **Закрыть**, который закрывает контексты устройства метафайла и возвращает дескриптор метафайла.  Затем удалите объекта `CMetaFileDC`.  
  
 [CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md) затем может использовать дескриптор метафайла для воспроизведения метафайл.  Метафайл также может быть манипулирован функциями Windows, как [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), который копирует метафайл на диск.  
  
 Если метафайл больше не требуется, удалите его из памяти с помощью функции [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows.  
  
 Кроме того, можно реализовывать объект `CMetaFileDC` таким образом, чтобы он мог обрабатывать и выводит вызовы и вызовы производного приписать GDI как `GetTextExtent`.  Такой метафайл является более гибким и может больше GDI легко общего повторного использования кода, который часто состоит из смешивания вывода и атрибут вызывает.  Класс `CMetaFileDC` наследует 2 контекста устройства, `m_hDC` и `m_hAttribDC`, из `CDC`.  Контекст устройства `m_hDC` обрабатывает все вызовы вывода GDI [CDC](../Topic/CDC%20Class.md) и маркеры контекста устройства `m_hAttribDC` все вызовы атрибута GDI `CDC`.  Обычно эти контексты 2 устройств ссылаются на один накопитель.  В случае `CMetaFileDC`, контроллер домена атрибута установлен в каталог по умолчанию **NULL**.  
  
 Создайте второй контекст устройства, указывающий на экране, принтера или устройство, за исключением метафайла, затем вызовите функцию\-член `SetAttribDC` чтобы связать новый контекст устройства с `m_hAttribDC`.  Вызовы GDI данных теперь направляются к новому `m_hAttribDC`.  Вызовы GDI вывода пойдут к `m_hDC`, который представляет метафайл.  
  
 Дополнительные сведения о `CMetaFileDC` см. в разделе [контексты устройства](../Topic/Device%20Contexts.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CMetaFileDC`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [Класс CDC](../Topic/CDC%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)