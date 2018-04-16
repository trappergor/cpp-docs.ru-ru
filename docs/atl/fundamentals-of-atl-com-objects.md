---
title: Основные принципы работы COM-объекты ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5a43af31a88420c154d7a57d27d2b69787d11d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fundamentals-of-atl-com-objects"></a>Основные принципы работы COM-объекты ATL
На следующем рисунке показана связь между классы и интерфейсы, которые используются для определения ATL COM-объекта.  
  
 ![Структура ATL](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  На этой диаграмме показано, что `CComObject` является производным от `CYourClass` в то время как `CComAggObject` и `CComPolyObject` включают `CYourClass` как переменную-член.  
  
 Существует три способа определения ATL COM-объекта. Стандартный вариант — использовать `CComObject` класс, производный от `CYourClass`. Второй параметр — Создание вычисляемого объекта с помощью `CComAggObject` класса. Третий вариант — использовать `CComPolyObject` класса. `CComPolyObject`выступает в качестве гибридной: он может работать как `CComObject` класса или как `CComAggObject` класса, в зависимости от того, как он впервые создается. Дополнительные сведения об использовании `CComPolyObject` см. в описании [CComPolyObject класса](../atl/reference/ccompolyobject-class.md).  
  
 При использовании стандартных ATL COM, можно использовать два объекта: объект внешнего и внутреннего объекта. Внешним клиентам доступ к функциям внутреннего объекта через функции-оболочки, которые определены в внешнего объекта. Внешний объект имеет тип `CComObject`.  
  
 При использовании вычисляемого объекта внешний объект не предоставляет программы-оболочки для функциональности внутреннего объекта. Вместо этого внешний объект предоставляет указатель, который осуществляется непосредственно с внешним клиентам. В этом случае внешний объект имеет тип `CComAggObject`. Внутренний объект является переменной-членом внешнего объекта и имеет тип `CYourClass`.  
  
 Поскольку клиент не придется проходить через внешний объект для взаимодействия с внутренний объект, статистические объекты обычно более эффективны. Кроме того внешний объект не требуется знать функции объекта статистические учитывая, что интерфейс сводный объект доступен напрямую клиенту. Однако не все объекты могут быть агрегированными. Объект статистической обработки ему следует проектировать с статистической обработки в виду.  
  
 Реализует ATL [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) в два этапа:  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), или [CComPolyObject](../atl/reference/ccompolyobject-class.md) реализует **IUnknown** методы.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляет подсчетом ссылок и внешнее указатели **IUnknown**.  
  
 Другие аспекты ATL COM-объект обрабатываются другими классами.  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) определяет объекта по умолчанию класс фабрики и статистической обработки модели.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) предоставляет реализацию по умолчанию `IDispatch Interface` часть любой сдвоенные интерфейсы в объекте.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) реализует **ISupportErrorInfo** интерфейс, который обеспечивает сведения об ошибках могут копироваться в цепочке вызовов правильно.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Реализация CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)  
 Показать пример записях сопоставления COM. для реализации `CComObjectRootEx`.  
  
 [Реализация CComObject, CComAggObject и CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Рассматриваются как **DECLARE_\*_AGGREGATABLE** макросы влияет на использование `CComObject`, `CComAggObject`, и `CComPolyObject`.  
  
 [Поддержка IDispatch и IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Список классов ATL реализации для поддержки `IDispatch` и **IErrorInfo** интерфейсов.  
  
 [Поддержка IDispEventImpl](../atl/supporting-idispeventimpl.md)  
 Описывает шаги по реализации точки подключения для класса.  
  
 [Изменение модели агрегирования и фабрики класса по умолчанию](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Показать макросы, используйте для изменения модели фабрики и статистической обработки классов по умолчанию.  
  
 [Создание объединенного объекта](../atl/creating-an-aggregated-object.md)  
 Приводятся инструкции по созданию вычисляемого объекта.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Создание проекта ATL](../atl/reference/creating-an-atl-project.md)  
 Сведения о создании ATL COM-объекта.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

