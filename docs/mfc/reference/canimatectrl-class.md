---
title: "CAnimateCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "animation controls [C++], CAnimateCtrl class"
  - "CAnimateCtrl class"
  - "Windows common controls [C++], CAnimateCtrl class"
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAnimateCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности управления Windows общего анимации.  
  
## Синтаксис  
  
```  
  
class CAnimateCtrl : public CWnd  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimateCtrl::CAnimateCtrl](../Topic/CAnimateCtrl::CAnimateCtrl.md)|Создает объект `CAnimateCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAnimateCtrl::Close](../Topic/CAnimateCtrl::Close.md)|Закрывает клип формат AVI.|  
|[CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)|Создает элемент управления "анимация" и вложение его к объекту `CAnimateCtrl`.|  
|[CAnimateCtrl::CreateEx](../Topic/CAnimateCtrl::CreateEx.md)|Создает элемент управления "анимация" с заданными стилей расширенными Windows и вложение его к объекту `CAnimateCtrl`.|  
|[CAnimateCtrl::IsPlaying](../Topic/CAnimateCtrl::IsPlaying.md)|Указывает, воспроизводит ли клип формат AVI \(формат AVI\).|  
|[CAnimateCtrl::Open](../Topic/CAnimateCtrl::Open.md)|Открывает клип формат AVI из файла или ресурса и указывает первый фрейм.|  
|[CAnimateCtrl::Play](../Topic/CAnimateCtrl::Play.md)|Воспроизводит клип формат AVI без звука.|  
|[CAnimateCtrl::Seek](../Topic/CAnimateCtrl::Seek.md)|Отображает выбранный формат AVI один кадр отсечения.|  
|[CAnimateCtrl::Stop](../Topic/CAnimateCtrl::Stop.md)|Останавливает воспроизведения клип формат AVI.|  
  
## Заметки  
 Этот элемент управления \(и, следовательно, класс `CAnimateCtrl` \) доступны только для программ, выполняемых в рамках версии 3.51, Windows 95, Windows 98 и Windows NT и более поздних версий.  
  
 Элемент управления "анимация" прямоугольное окно, в котором отображается клип в форме формат AVI \(формат AVI\) стандартного звукового формат\/видео Windows.  Клип формат AVI ряд кадров растрового изображения, например фильм.  
  
 Управления анимации могут воспроизведения только простые фрагменты формат AVI.  В частности, фрагменты, который будет играть элемент управления "анимация" должны удовлетворять следующим требованиям:  
  
-   Должно быть ровно один поток видео и он должен иметь по крайней мере один кадр.  
  
-   Могут быть максимум 2 потока в файле \(обычно другой поток, если он имеется, аудиопоток, то элемент управления "анимация" не учитывает звуковых данных подробности\).  
  
-   Клип должен быть несжат или уменьшена со сжатием RLE8.  
  
-   Не разрешены изменение цветов в видео потока.  
  
 Клип формат AVI можно добавить в приложение в виде ресурса формат AVI или оно может сопроводить приложение как отдельный файл формата AVI.  
  
 Так как этот поток продолжает выполняться, пока клип формат AVI отображается одна для управления анимацией обычно используется для отображения действие системы во время длительной операции.  Например, диалоговое окно поиска обозревателя файлов показывает, перемещающиеся лупу, как поиск системы для файла.  
  
 При создании объекта `CAnimateCtrl` в диалоговое окно или из ресурса диалогового окна с помощью редактора диалоговых окон, то он будет автоматически уничтожается, когда пользователь закрывает диалоговое окно.  
  
 При создании объекта `CAnimateCtrl` в окне, можно удалить его.  При создании объекта `CAnimateCtrl` в стеке, он удален автоматически.  При создании объекта `CAnimateCtrl` в куче с помощью функции **новый**, необходимо вызвать метод **удалить** объекта, чтобы удалить его.  При наследовании новый класс, производный от `CAnimateCtrl` и выберите любая память в этом классе, следует переопределить `CAnimateCtrl` деструктор для удаления распределений.  
  
 Дополнительные сведения об использовании `CAnimateCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CAnimateCtrl](../Topic/Using%20CAnimateCtrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CAnimateCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)   
 [ON\_CONTROL](../Topic/ON_CONTROL.md)