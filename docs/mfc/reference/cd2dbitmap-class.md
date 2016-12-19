---
title: "Класс CD2DBitmap | Microsoft Docs"
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
  - "afxrendertarget/CD2DBitmap"
  - "CD2DBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmap - класс"
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DBitmap
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1Bitmap.  
  
## Синтаксис  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|Перегружен.  Создает объект CD2DBitmap из HBITMAP.|  
|[CD2DBitmap::~CD2DBitmap](../Topic/CD2DBitmap::~CD2DBitmap.md)|Деструктор.  Вызывается при уничтожении объекта растрового изображения D2D.|  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|Перегружен.  Создает объект CD2DBitmap.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmap::Attach](../Topic/CD2DBitmap::Attach.md)|Присоединяет интерфейс существующего ресурса к объекту|  
|[CD2DBitmap::CopyFromBitmap](../Topic/CD2DBitmap::CopyFromBitmap.md)|Копирует заданную область из заданного растрового изображения в текущее растровое изображение|  
|[CD2DBitmap::CopyFromMemory](../Topic/CD2DBitmap::CopyFromMemory.md)|Копирует заданную область из памяти в текущее растровое изображение|  
|[CD2DBitmap::CopyFromRenderTarget](../Topic/CD2DBitmap::CopyFromRenderTarget.md)|Копирует заданную область из заданного целевого буфера визуализации в текущее растровое изображение|  
|[CD2DBitmap::Create](../Topic/CD2DBitmap::Create.md)|Создает объект CD2DBitmap.  \(Переопределяет [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DBitmap::Destroy](../Topic/CD2DBitmap::Destroy.md)|Уничтожает объект CD2DBitmap.  \(Переопределяет [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DBitmap::Detach](../Topic/CD2DBitmap::Detach.md)|Отсоединяет интерфейс ресурса от объекта|  
|[CD2DBitmap::Get](../Topic/CD2DBitmap::Get.md)|Возвращает интерфейс ID2D1Bitmap|  
|[CD2DBitmap::GetDPI](../Topic/CD2DBitmap::GetDPI.md)|Возвращает разрешение растрового изображения в точках на дюйм.|  
|[CD2DBitmap::GetPixelFormat](../Topic/CD2DBitmap::GetPixelFormat.md)|Извлекает формат пикселей и альфа\-режим растрового изображения|  
|[CD2DBitmap::GetPixelSize](../Topic/CD2DBitmap::GetPixelSize.md)|Возвращает размер растрового изображения в аппаратно\-зависимых единицах \(пикселях\)|  
|[CD2DBitmap::GetSize](../Topic/CD2DBitmap::GetSize.md)|Исходный размер растрового изображения в аппаратно\-независимых пикселях \(DIP\)|  
|[CD2DBitmap::IsValid](../Topic/CD2DBitmap::IsValid.md)|Проверяет допустимость ресурса \(переопределяет [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmap::CommonInit](../Topic/CD2DBitmap::CommonInit.md)|Инициализирует объект|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmap::operator ID2D1Bitmap\*](../Topic/CD2DBitmap::operator%20ID2D1Bitmap*.md)|Возвращает интерфейс ID2D1Bitmap|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmap::m\_bAutoDestroyHBMP](../Topic/CD2DBitmap::m_bAutoDestroyHBMP.md)|Значение TRUE, если m\_hBmpSrc должен быть уничтожен; в противном случае — значение FALSE.|  
|[CD2DBitmap::m\_hBmpSrc](../Topic/CD2DBitmap::m_hBmpSrc.md)|Дескриптор исходного растрового изображения.|  
|[CD2DBitmap::m\_lpszType](../Topic/CD2DBitmap::m_lpszType.md)|Тип ресурса.|  
|[CD2DBitmap::m\_pBitmap](../Topic/CD2DBitmap::m_pBitmap.md)|Хранит указатель на объект ID2D1Bitmap.|  
|[CD2DBitmap::m\_sizeDest](../Topic/CD2DBitmap::m_sizeDest.md)|Размер целевого объекта растрового изображения.|  
|[CD2DBitmap::m\_strPath](../Topic/CD2DBitmap::m_strPath.md)|Путь к файлу растрового изображения.|  
|[CD2DBitmap::m\_uiResID](../Topic/CD2DBitmap::m_uiResID.md)|Идентификатор ресурса растрового изображения.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBitmap](../../mfc/reference/cd2dbitmap-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)