---
title: Основы COM-объекты ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9dc87340d567f876d91abc4d8ebfa1d6353cad
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209991"
---
# <a name="fundamentals-of-atl-com-objects"></a>Основы COM-объектов ATL
На следующем рисунке показана связь между классы и интерфейсы, которые используются для определения ATL COM-объекта.  
  
 ![Структура ATL](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  На этой схеме показано, что `CComObject` является производным от `CYourClass` то время как `CComAggObject` и `CComPolyObject` включают `CYourClass` как переменную-член.  
  
 Существует три способа определения ATL COM-объекта. Стандартный вариант — использовать `CComObject` класс, производный от `CYourClass`. Второй вариант — Создание объединенного объекта с помощью `CComAggObject` класса. Третий вариант — использовать `CComPolyObject` класса. `CComPolyObject` выступает в качестве гибридной: он может работать как `CComObject` класс или как `CComAggObject` класса, в зависимости от того, как он впервые создается. Дополнительные сведения об использовании `CComPolyObject` , представлена в разделе [класс CComPolyObject](../atl/reference/ccompolyobject-class.md).  
  
 При использовании стандартных COM ATL, можно использовать два объекта: объект внешнего и внутреннего объекта. Внешним клиентам доступ к функциям внутренний объект посредством функции-оболочки, которые определены в внешний объект. Внешний объект имеет тип `CComObject`.  
  
 При использовании объединенного объекта внешний объект не предоставляет оболочки для функциональности внутреннего объекта. Вместо этого внешний объект предоставляет указатель, который осуществляется непосредственно с внешними клиентами. В этом случае внешний объект имеет тип `CComAggObject`. Внутренний объект является переменной-членом внешнего объекта, и он имеет тип `CYourClass`.  
  
 Так как клиент не проходят через внешний объект для взаимодействия с внутренний объект, объединенные объекты обычно более эффективны. Кроме того внешний объект не нужно знать функциональность агрегированные объекта, учитывая, что интерфейс агрегированные объекта непосредственно доступен клиенту. Тем не менее может быть статистически вычислена не все объекты. Выполнить статистическую обработку объекта она должна разрабатываться с помощью статистической обработки в виду.  
  
 Реализует ATL [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) состоит из двух этапов:  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), или [CComPolyObject](../atl/reference/ccompolyobject-class.md) реализует `IUnknown` методы.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляет счетчик ссылок и внешнее указатели `IUnknown`.  
  
 Другие аспекты ATL COM-объект, обрабатываются другими классами.  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) определяет объекта по умолчанию класс фабрики и статистическую обработку модели.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) предоставляет реализацию по умолчанию `IDispatch Interface` часть любого сдвоенные интерфейсы в объекте.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) реализует `ISupportErrorInfo` интерфейса, которое гарантирует, что сведения об ошибках могут передаваться вверх по цепи вызова правильно.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Реализация CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)  
 Показать пример записи сопоставления COM для реализации `CComObjectRootEx`.  
  
 [Реализация CComObject, CComAggObject и CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Рассматриваются как **DECLARE_\*_AGGREGATABLE** макросы влияют на использование `CComObject`, `CComAggObject`, и `CComPolyObject`.  
  
 [Поддержка IDispatch и IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Список классов ATL реализации для поддержки `IDispatch` и `IErrorInfo` интерфейсов.  
  
 [Поддержка IDispEventImpl](../atl/supporting-idispeventimpl.md)  
 Описывает шаги по реализации точки подключения для вашего класса.  
  
 [Изменение модели агрегирования и фабрики класса по умолчанию](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Показано, какие макросы, чтобы использовать для изменения модели фабрики и статистической обработки классов по умолчанию.  
  
 [Создание объединенного объекта](../atl/creating-an-aggregated-object.md)  
 Приводятся инструкции по созданию вычисляемого объекта.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Создание проекта ATL](../atl/reference/creating-an-atl-project.md)  
 Содержит сведения о создании ATL COM-объекта.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

