---
title: "Класс CRenderTarget | Microsoft Docs"
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
  - "CRenderTarget"
  - "afxrendertarget/CRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRenderTarget - класс"
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CRenderTarget
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1RenderTarget.  
  
## Синтаксис  
  
```  
class CRenderTarget : public CObject;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRenderTarget::CRenderTarget](../Topic/CRenderTarget::CRenderTarget.md)|Создает объект CRenderTarget.|  
|[CRenderTarget::~CRenderTarget](../Topic/CRenderTarget::~CRenderTarget.md)|Деструктор.  Вызывается при уничтожении объекта целевого буфера визуализации.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRenderTarget::Attach](../Topic/CRenderTarget::Attach.md)|Присоединяет интерфейс существующего целевого буфера визуализации к объекту|  
|[CRenderTarget::BeginDraw](../Topic/CRenderTarget::BeginDraw.md)|Инициирует рисование в данном целевом буфере визуализации.|  
|[CRenderTarget::Clear](../Topic/CRenderTarget::Clear.md)|Очищает область рисования до заданного цвета.|  
|[CRenderTarget::COLORREF\_TO\_D2DCOLOR](../Topic/CRenderTarget::COLORREF_TO_D2DCOLOR.md)|Преобразует значения цвета и альфа\-значения GDI в объект D2D1\_COLOR\_F.|  
|[CRenderTarget::CreateCompatibleRenderTarget](../Topic/CRenderTarget::CreateCompatibleRenderTarget.md)|Создает новый целевой буфер визуализации растрового изображения для использования во время промежуточной прорисовки за пределами экрана, совместимый с текущим целевым буфером визуализации.|  
|[CRenderTarget::Destroy](../Topic/CRenderTarget::Destroy.md)|Удаляет один или несколько ресурсов|  
|[CRenderTarget::Detach](../Topic/CRenderTarget::Detach.md)|Отсоединяет интерфейс целевого буфера визуализации от объекта|  
|[CRenderTarget::DrawBitmap](../Topic/CRenderTarget::DrawBitmap.md)|Рисует форматированный текст, описанный заданным объектом IDWriteTextLayout.|  
|[CRenderTarget::DrawEllipse](../Topic/CRenderTarget::DrawEllipse.md)|Рисует контур заданного эллипса, используя заданный стиль обводки.|  
|[CRenderTarget::DrawGeometry](../Topic/CRenderTarget::DrawGeometry.md)|Рисует контур заданной геометрии, используя заданный стиль обводки.|  
|[CRenderTarget::DrawGlyphRun](../Topic/CRenderTarget::DrawGlyphRun.md)|Рисует заданные глифы.|  
|[CRenderTarget::DrawLine](../Topic/CRenderTarget::DrawLine.md)|Рисует линию между заданными точками, используя заданный стиль обводки.|  
|[CRenderTarget::DrawRectangle](../Topic/CRenderTarget::DrawRectangle.md)|Рисует контур прямоугольника, имеющий заданные размеры и стиль обводки.|  
|[CRenderTarget::DrawRoundedRectangle](../Topic/CRenderTarget::DrawRoundedRectangle.md)|Рисует контур заданного скругленного прямоугольника, используя заданный стиль обводки.|  
|[CRenderTarget::DrawText](../Topic/CRenderTarget::DrawText.md)|Рисует заданный текст, используя информацию о формате, предоставленную объектом IDWriteTextFormat.|  
|[CRenderTarget::DrawTextLayout](../Topic/CRenderTarget::DrawTextLayout.md)|Рисует форматированный текст, описанный заданным объектом IDWriteTextLayout.|  
|[CRenderTarget::EndDraw](../Topic/CRenderTarget::EndDraw.md)|Завершает операции рисования в целевом буфере визуализации и указывает текущее состояние ошибки и соответствующие теги.|  
|[CRenderTarget::FillEllipse](../Topic/CRenderTarget::FillEllipse.md)|Закрашивает внутреннюю область заданного эллипса.|  
|[CRenderTarget::FillGeometry](../Topic/CRenderTarget::FillGeometry.md)|Закрашивает внутреннюю область заданной геометрии.|  
|[CRenderTarget::FillMesh](../Topic/CRenderTarget::FillMesh.md)|Закрашивает внутреннюю область заданной сетки.|  
|[CRenderTarget::FillOpacityMask](../Topic/CRenderTarget::FillOpacityMask.md)|Применяет маску прозрачности, описанную заданным растровым изображением, к кисти, и с помощью этой кисти окрашивает область целевого буфера визуализации.|  
|[CRenderTarget::FillRectangle](../Topic/CRenderTarget::FillRectangle.md)|Закрашивает внутреннюю область заданного прямоугольника.|  
|[CRenderTarget::FillRoundedRectangle](../Topic/CRenderTarget::FillRoundedRectangle.md)|Закрашивает внутреннюю область заданного скругленного прямоугольника.|  
|[CRenderTarget::Flush](../Topic/CRenderTarget::Flush.md)|Выполняет все ожидающие команды рисования.|  
|[CRenderTarget::GetAntialiasMode](../Topic/CRenderTarget::GetAntialiasMode.md)|Извлекает текущий режим сглаживания для нетекстовых операций рисования.|  
|[CRenderTarget::GetDpi](../Topic/CRenderTarget::GetDpi.md)|Возвращает разрешение целевого буфера визуализации в DPI|  
|[CRenderTarget::GetMaximumBitmapSize](../Topic/CRenderTarget::GetMaximumBitmapSize.md)|Получает максимальную величину в аппаратно\-зависимых единицах \(пикселях\) любого одного размера растрового изображения, поддерживаемую целевым буфером визуализации.|  
|[CRenderTarget::GetPixelFormat](../Topic/CRenderTarget::GetPixelFormat.md)|Извлекает формат пикселей и альфа\-режим целевого буфера визуализации|  
|[CRenderTarget::GetPixelSize](../Topic/CRenderTarget::GetPixelSize.md)|Возвращает размер целевого буфера визуализации в аппаратно\-зависимых пикселях|  
|[CRenderTarget::GetRenderTarget](../Topic/CRenderTarget::GetRenderTarget.md)|Возвращает интерфейс ID2D1RenderTarget|  
|[CRenderTarget::GetSize](../Topic/CRenderTarget::GetSize.md)|Возвращает размер целевого буфера визуализации в аппаратно\-независимых пикселях|  
|[CRenderTarget::GetTags](../Topic/CRenderTarget::GetTags.md)|Получает метку для последующих операций рисования.|  
|[CRenderTarget::GetTextAntialiasMode](../Topic/CRenderTarget::GetTextAntialiasMode.md)|Получает текущий режим сглаживания для операций рисования текста и глифов.|  
|[CRenderTarget::GetTextRenderingParams](../Topic/CRenderTarget::GetTextRenderingParams.md)|Извлекает текущие параметры отрисовки текста целевого буфера отрисовки.|  
|[CRenderTarget::GetTransform](../Topic/CRenderTarget::GetTransform.md)|Применяет заданное преобразование к целевому объекту визуализации, замещая существующее преобразование.  Все последующие операции рисования имеют место в преобразованном пространстве.|  
|[CRenderTarget::IsSupported](../Topic/CRenderTarget::IsSupported.md)|Указывает, поддерживает ли целевой буфер визуализации заданные свойства|  
|[CRenderTarget::IsValid](../Topic/CRenderTarget::IsValid.md)|Проверяет допустимость ресурса|  
|[CRenderTarget::PopAxisAlignedClip](../Topic/CRenderTarget::PopAxisAlignedClip.md)|Удаляет последнее выровненное по оси отсечение из целевого буфера визуализации.  После вызова этого метода отсечение более не применяется к последующим операциям рисования.|  
|[CRenderTarget::PopLayer](../Topic/CRenderTarget::PopLayer.md)|Прекращает перенаправление операций рисования на слой, заданный последним вызовом метода PushLayer.|  
|[CRenderTarget::PushAxisAlignedClip](../Topic/CRenderTarget::PushAxisAlignedClip.md)|Удаляет последнее выровненное по оси отсечение из целевого буфера визуализации.  После вызова этого метода отсечение более не применяется к последующим операциям рисования.|  
|[CRenderTarget::PushLayer](../Topic/CRenderTarget::PushLayer.md)|Добавляет заданный слой в целевой буфер визуализации, чтобы он получал все последующие операции рисования до вызова метода PopLayer.|  
|[CRenderTarget::RestoreDrawingState](../Topic/CRenderTarget::RestoreDrawingState.md)|Устанавливает состояние рисования целевого буфера визуализации равным состоянию заданного объекта ID2D1DrawingStateBlock.|  
|[CRenderTarget::SaveDrawingState](../Topic/CRenderTarget::SaveDrawingState.md)|Сохраняет текущее состояние рисования в заданный объект ID2D1DrawingStateBlock.|  
|[CRenderTarget::SetAntialiasMode](../Topic/CRenderTarget::SetAntialiasMode.md)|Устанавливает режим сглаживания для целевого буфера визуализации.  Режим сглаживания применяется ко всем последующим операциям рисования, за исключением операций рисования текста и глифов.|  
|[CRenderTarget::SetDpi](../Topic/CRenderTarget::SetDpi.md)|Устанавливает разрешение целевого буфера визуализации в DPI.|  
|[CRenderTarget::SetTags](../Topic/CRenderTarget::SetTags.md)|Задает метку для последующих операций рисования.|  
|[CRenderTarget::SetTextAntialiasMode](../Topic/CRenderTarget::SetTextAntialiasMode.md)|Задает режим сглаживания для последующих операций рисования текста и глифов.|  
|[CRenderTarget::SetTextRenderingParams](../Topic/CRenderTarget::SetTextRenderingParams.md)|Задает параметры отрисовки текста, применяемые ко всем последующим операциям рисования текста и глифов.|  
|[CRenderTarget::SetTransform](../Topic/CRenderTarget::SetTransform.md)|Перегружен.  Применяет заданное преобразование к целевому объекту визуализации, замещая существующее преобразование.  Все последующие операции рисования имеют место в преобразованном пространстве.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRenderTarget::VerifyResource](../Topic/CRenderTarget::VerifyResource.md)|Проверяет объект CD2DResource на допустимость; создает объект, если он еще не существует.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRenderTarget::operator ID2D1RenderTarget\*](../Topic/CRenderTarget::operator%20ID2D1RenderTarget*.md)|Возвращает интерфейс ID2D1RenderTarget|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CRenderTarget::m\_lstResources](../Topic/CRenderTarget::m_lstResources.md)|Список указателей на объекты CD2DResource.|  
|[CRenderTarget::m\_pRenderTarget](../Topic/CRenderTarget::m_pRenderTarget.md)|Указатель на объект ID2D1RenderTarget.|  
|[CRenderTarget::m\_pTextFormatDefault](../Topic/CRenderTarget::m_pTextFormatDefault.md)|Указатель на объект CD2DTextFormat, содержащий формат текста по умолчанию.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)