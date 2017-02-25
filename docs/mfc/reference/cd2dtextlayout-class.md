---
title: "Класс CD2DTextLayout | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DTextLayout"
  - "afxrendertarget/CD2DTextLayout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextLayout - класс"
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс CD2DTextLayout
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для IDWriteTextLayout.  
  
## Синтаксис  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DTextLayout::CD2DTextLayout](../Topic/CD2DTextLayout::CD2DTextLayout.md)|Создает объект CD2DTextLayout.|  
|[CD2DTextLayout::~CD2DTextLayout](../Topic/CD2DTextLayout::~CD2DTextLayout.md)|Деструктор.  Вызывается при уничтожении объекта макета текста D2D.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DTextLayout::Create](../Topic/CD2DTextLayout::Create.md)|Создает объект CD2DTextLayout.  \(Переопределяет [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DTextLayout::Destroy](../Topic/CD2DTextLayout::Destroy.md)|Уничтожает объект CD2DTextLayout.  \(Переопределяет [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DTextLayout::Get](../Topic/CD2DTextLayout::Get.md)|Возвращает интерфейс IDWriteTextLayout|  
|[CD2DTextLayout::GetFontFamilyName](../Topic/CD2DTextLayout::GetFontFamilyName.md)|Копирует имя семейства шрифтов текста в заданной позиции.|  
|[CD2DTextLayout::GetLocaleName](../Topic/CD2DTextLayout::GetLocaleName.md)|Получает имя языкового стандарта текста в заданной позиции.|  
|[CD2DTextLayout::IsValid](../Topic/CD2DTextLayout::IsValid.md)|Проверяет допустимость ресурса \(переопределяет [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DTextLayout::ReCreate](../Topic/CD2DTextLayout::ReCreate.md)|Повторно создает объект CD2DTextLayout.  \(Переопределяет [CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md).\)|  
|[CD2DTextLayout::SetFontFamilyName](../Topic/CD2DTextLayout::SetFontFamilyName.md)|Устанавливает заканчивающееся нулем имя семейства шрифтов для текста в пределах заданного диапазона текста|  
|[CD2DTextLayout::SetLocaleName](../Topic/CD2DTextLayout::SetLocaleName.md)|Устанавливает имя языкового стандарта для текста в пределах заданного диапазона текста|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DTextLayout::operator IDWriteTextLayout\*](../Topic/CD2DTextLayout::operator%20IDWriteTextLayout*.md)|Возвращает интерфейс IDWriteTextLayout|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DTextLayout::m\_pTextLayout](../Topic/CD2DTextLayout::m_pTextLayout.md)|Указатель на IDWriteTextLayout.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)