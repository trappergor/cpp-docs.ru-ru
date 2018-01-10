---
title: "Основные понятия шаблонных Library (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7cf2568005049cfabd9178ea4c8732a5a985954
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="active-template-library-atl-concepts"></a>Основные понятия активной библиотеки шаблонных классов (ATL)
Active Template Library (ATL) — это набор основанных на шаблонах классов C++, которые позволяют создавать быстрый объекты модели объектов компонентов (COM). Он имеет специальную поддержку для ключевых компонентов COM, включая стандартные реализации, сдвоенные интерфейсы, стандартные интерфейсы перечислителя COM, точки подключения, перемещаемые интерфейсы и элементы управления ActiveX.  
  
 Если делается множество ATL-программированию, необходимо для получения дополнительных сведений об атрибутах, появившаяся в Visual C++ .NET, который предназначен для упрощения программирования в модели COM. Дополнительные сведения см. в разделе [атрибутивного программирования](../windows/attributed-programming-concepts.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Учебник по ATL](../atl/active-template-library-atl-tutorial.md)  
 Описание создания элементов управления и некоторые основные принципы ATL в процессе.  
  
 [Введение в модель COM и ATL](../atl/introduction-to-com-and-atl.md)  
 Понятия основных за объекта модели компонентов (COM). В этой статье также приводится краткое описание возможности ATL и когда его следует использовать.  
  
 [Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)  
 Описывает связь между различные классы ATL и порядок реализации этих классов.  
  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)  
 Описывает сдвоенные интерфейсы с точки зрения ATL.  
  
 [Коллекции и перечислители ATL](../atl/atl-collections-and-enumerators.md)  
 Описывает реализацию и создание коллекции и перечислители в ATL  
  
 [Принципы работы составного элемента управления](../atl/atl-composite-control-fundamentals.md)  
 Содержит пошаговые инструкции для создания составного элемента управления. Составной элемент управления — это тип элемента управления ActiveX, который может содержать другие элементы управления ActiveX или элементы управления Windows.  
  
 [Часто задаваемые вопросы о вложении элементов управления ATL](../atl/atl-control-containment-faq.md)  
 Рассматриваются основные вопросы, связанные с размещением элементов управления с ATL  
  
 [Страницы свойств COM в ATL](../atl/atl-com-property-pages.md)  
 Показано, как задать и реализовать страницы свойств COM.  
  
 [Поддержка элементов управления DHTML в ATL](../atl/atl-support-for-dhtml-controls.md)  
 Содержит пошаговые инструкции по созданию элемента управления DHTML.  
  
 [Точки подключения ATL](../atl/atl-connection-points.md)  
 Описание точки подключения и как ATL реализует их.  
  
 [Обработка событий и ATL](../atl/event-handling-and-atl.md)  
 Описание действий, которые необходимо выполнить для обработки событий COM, ATL с помощью [IDispEventImpl](../atl/reference/idispeventimpl-class.md) и [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) классы.  
  
 [ATL и упаковщик в режиме свободного потока](../atl/atl-and-the-free-threaded-marshaler.md)  
 Содержит сведения о мастер простых объектов ATL параметр, позволяющий класса для статистической обработки свободного упаковщик в режиме потока (FTM).  
  
 [Указание потоковой модели проекта](../atl/specifying-the-threading-model-for-a-project-atl.md)  
 Описывает макросы, которые можно контролировать производительность во время выполнения, связанных с многопоточностью в своем проекте.  
  
 [Модульные классы ATL](../atl/atl-module-classes.md)  
 Описывает новые классы модуля в ATL 7.0. Классы модуля реализации базовой функциональности, необходимые для библиотеки ATL.  
  
 [Службы ATL](../atl/atl-services.md)  
 Описание последовательности событий, возникающих при реализации службы. Также рассказывается о некоторых понятий, относящихся к разработке службы.  
  
 [Классы окон ATL](../atl/atl-window-classes.md)  
 Описывает способы создания, суперкласса и подкласс windows в ATL Классы окон ATL не COM-классов.  
  
 [Классы коллекций ATL](../atl/atl-collection-classes.md)  
 Описывает, как использовать массивы и сопоставляет в ATL  
  
 [Компонент реестра ATL (регистратор)](../atl/atl-registry-component-registrar.md)  
 Описывает ATL сценариев синтаксиса и подстановочные параметры. Также объясняется, как настроить статическая компоновка с помощью регистратора.  
  
 [Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)  
 Описывает преимущества связывание статической или динамической библиотеки времени выполнения C (CRT).  
  
 [Программирование с использованием CComBSTR](../atl/programming-with-ccombstr-atl.md)  
 Описание различных ситуаций, требующих осторожность при программировании с `CComBSTR`.  
  
 [Справочник по кодировке](../atl/atl-encoding-reference.md)  
 Предоставляет функции и макросы, поддерживающие кодировка UTF8 и широкий набор общих стандартов Интернета как uuencode, в шестнадцатеричном виде, в файла atlenc.h.  
  
 [Справочник по служебным программам](../atl/atl-utilities-reference.md)  
 Предоставляет код для управления URL-адреса и пути в виде [CPathT](../atl/reference/cpatht-class.md) и [CUrl](../atl/reference/curl-class.md). Пул потоков [CThreadPool](../atl/reference/cthreadpool-class.md), можно использовать в собственных приложениях. Этот код можно найти в atlpath.h и файлов atlutil.h.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Образцы ATL](../visual-cpp-samples.md)  
 Предоставляет описания и ссылки на примеры программ ATL.  
  
 [Создание проекта ATL](../atl/reference/creating-an-atl-project.md)  
 Содержит сведения о мастере проекта ATL.  
  
 [Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md)  
 Описывает добавление классов.  
  
 [Атрибутивное программирование](../windows/attributed-programming-concepts.md)  
 Общие сведения об использовании атрибутов для упрощения программирования в модели COM, а также список ссылок на разделы с более подробными сведениями.  
  
 [Общие сведения о классах ATL](../atl/atl-class-overview.md)  
 Содержит справочные сведения и ссылки для ATL-классы.

