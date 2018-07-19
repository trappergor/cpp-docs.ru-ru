---
title: ATL классы и структуры | Документация Майкрософт
ms.custom: ''
ms.date: 05/03/2018
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb96db2ff3a927885bdb914665147dc0e7ce8da
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881296"
---
# <a name="atl-classes-and-structs"></a>Классы ATL и структуры
Active Template Library (ATL) включает следующие классы и структуры. Чтобы найти конкретный класс по категориям, см. в разделе [Обзор класса ATL](../../atl/atl-class-overview.md).  
  
|Класс или структура|Описание:|Файл заголовка|  
|-----------|-----------------|-----------------|  
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|Содержит сведения, используемые для подготовки к просмотру в различные целевые объекты, такие как принтер, метафайла или элемент управления ActiveX.|atlctl.h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|Содержит данные экземпляра класса в коде управления окнами в ATL|atlbase.h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|Используемые любого проекта, которое использует ATL.|atlbase.h|  
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|Используемый код, связанный с COM в ATL| atlbase.h|  
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|Содержит сведения о типе, используемые для описания метода или свойства на disp-интерфейсом.|atlcom.h|  
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|Содержит данные, используемые каждого модуля ATL.|atlbase.h|  
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|Используется кодом Управление окнами в ATL|atlbase.h|  
|[CA2AEX](../../atl/reference/ca2aex-class.md)|Этот класс используется, макросы преобразования строк CA2TEX CT2AEX и typedef CA2A.|atlconv.h|  
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|Этот класс используется, макросы преобразования строк CA2CTEX CT2CAEX и typedef CA2CA.|atlconv.h|  
|[CA2WEX](../../atl/reference/ca2wex-class.md)|Этот класс используется, макросы преобразования строк CA2TEX, CA2CTEX, CT2WEX и CT2CWEX и typedef CA2W.|atlconv.h|  
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|Этот класс является оболочкой для маркера доступа.|ATLSecurity.h|  
|[CAcl](../../atl/reference/cacl-class.md)|Этот класс является оболочкой для структуры ACL (список управления доступом).|ATLSecurity.h|  
|[CAdapt](../../atl/reference/cadapt-class.md)|Этот шаблон используется для создания оболочек классов, переопределяющих оператор взятия адреса, чтобы он возвращал нечто, отличное от адреса объекта.|atlcomcli.h|  
|[CAtlArray](../../atl/reference/catlarray-class.md)|Этот класс реализует объект массива.|atlcoll.h|  
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|Этот класс реализует COM-сервера пула потоков, модель с подразделением.|atlbase.h|  
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|Этот класс предоставляет методы для реализации пула потоков, модель с подразделением COM-сервера.|atlbase.h|  
|[CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)|В каждом проекте ATL создается экземпляр этого класса.|файле atlcore.h|  
|[CAtlComModule](../../atl/reference/catlcommodule-class.md)|Этот класс реализует COM-модуля сервера.|atlbase.h|  
|[CAtlDebugInterfacesModule](../../atl/reference/catldebuginterfacesmodule-class.md)|Этот класс поддерживает интерфейсы отладки.|atlbase.h|  
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|Этот класс представляет модуль для библиотеки DLL.|atlbase.h|  
|[CAtlException](../../atl/reference/catlexception-class.md)|Этот класс определяет ATL исключения.|atlexcept.h|  
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|Этот класс представляет модуль для приложения.|atlbase.h|  
|[CAtlFile](../../atl/reference/catlfile-class.md)|Этот класс предоставляет тонкую оболочку Windows API обработки файлов.|atlfile.h|  
|[CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)|Этот класс представляет размещенного в памяти файла, добавление оператора приведения к методам [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).|atlfile.h|  
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|Этот класс представляет файл, размещенный в памяти.|atlfile.h|  
|[CAtlList](../../atl/reference/catllist-class.md)|Этот класс предоставляет методы для создания и управления объект списка.|atlcoll.h|  
|[CAtlMap](../../atl/reference/catlmap-class.md)|Этот класс предоставляет методы для создания и управления объект карты.|atlcoll.h|  
|[CAtlModule](../../atl/reference/catlmodule-class.md)|Этот класс предоставляет методы, используемые несколькими модульные классы ATL.|atlbase.h|  
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|Этот класс реализует модуль ATL.|atlbase.h|  
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|Этот класс является реализацией ATL окна, которое помещается в окне узла, заданного оболочкой для расширенного просмотра.|atlpreviewctrlimpl.h|  
|[CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|Этот класс реализует службу.|atlbase.h|  
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|Этот класс предоставляет методы для создания и использования временных файлов.|atlfile.h|  
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|Этот класс предоставляет оболочку для функции диспетчера транзакций ядра (KTM).|atltransactionmanager.h|  
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|Этот класс обеспечивает поддержку для работы с окнами компоненты ATL.|atlbase.h|  
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|Этот класс представляет объект интеллектуального указателя.|atlbase.h|  
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|Этот класс предоставляет методы, используемые при создании массива интеллектуальных указателей.|atlbase.h|  
|[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекции интеллектуальных указателей.|atlcoll.h|  
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|Этот класс предоставляет методы, используемые при построении списка интеллектуальные указатели.|atlcoll.h|  
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|Этот класс представляет объект интеллектуального указателя с помощью вектора новый и удалять операторов.|atlbase.h|  
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов, полезных при создании коллекции с помощью вектора новый интеллектуальных указателей и удалять операторов.|atlcoll.h|  
|[CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)|Этот класс реализует диалоговое окно (модальное или немодальное), на котором размещены элементы управления ActiveX.|atlwin.h|  
|[CAxWindow](../../atl/reference/caxwindow-class.md)|Этот класс предоставляет методы для работы с окном, размещения элемента управления ActiveX.|atlwin.h|  
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|Этот класс предоставляет методы для работы с окном, которое размещает элемент ActiveX, а также поддержку размещения Лицензированные элементы управления ActiveX.|atlwin.h|  
|[CBindStatusCallback](../../atl/reference/cbindstatuscallback-class.md)|Этот класс реализует интерфейс `IBindStatusCallback`.|atlctl.h|  
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для объединенного объекта.|atlcom.h|  
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|Этот класс предоставляет методы для управления памяти с помощью COM памяти подпрограммы.|atlbase.h|  
|[CComApartment](../../atl/reference/ccomapartment-class.md)|Этот класс предоставляет поддержку для управления подразделение в модуле EXE потоков в составе пула.|atlbase.h|  
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|Этот класс предоставляет методы для получения и освобождения владения объект критической секции.|файле atlcore.h|  
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|По состоянию на ATL 7.0 `CComAutoThreadModule` является устаревшим: см. в разделе [модули ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.|atlbase.h|  
|[CComBSTR](../../atl/reference/ccombstr-class.md)|Этот класс является оболочкой для строк BSTR.|atlbase.h|  
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для перемещаемой интерфейса.|atlcom.h|  
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейс.|atlcom.h|  
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|Этот класс реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс.|atlcom.h|  
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейс, а также позволяет создавать в нескольких подразделениях объекты.|atlcom.h|  
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|Этот класс является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта.|atlcom.h|  
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|Этот класс предоставляет методы для создания экземпляров класса и получения его свойств.|atlcom.h|  
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|Этот класс предоставляет методы, необходимые для реализации составного элемента управления.|atlctl.h|  
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) делегируя владельца объекта `IUnknown`.|atlcom.h|  
|[CComControl](../../atl/reference/ccomcontrol-class.md)|Этот класс предоставляет методы для создания и управления элементами управления ATL.|atlctl.h|  
|[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)|Этот класс предоставляет методы для создания и управления элементами управления ATL.|atlctl.h|  
|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)|Этот класс предоставляет методы для получения и освобождения владения объект критической секции.|файле atlcore.h|  
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|Этот класс предоставляет методы для блокировки и разблокировки объект критической секции.|atlbase.h|  
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|Этот класс содержит методы и операторы для создания и управления объекта CURRENCY.|atlcur.h|  
|[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)|Этот класс содержит массив `IUnknown` указатели.|atlcom.h|  
|[CComEnum](../../atl/reference/ccomenum-class.md)|Этот класс определяет перечислитель COM-объекта на основе массива.|atlcom.h|  
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|Этот класс предоставляет реализацию интерфейса перечислителя COM, где хранятся перечисляемых элементов в массиве.|atlcom.h|  
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|Этот класс определяет перечислитель COM-объекта на основе коллекции стандартной библиотеки C++.|atlcom.h|  
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|Этот класс предоставляет те же методы, как [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , но не предоставляет критический раздел.|файле atlcore.h|  
|[CComGITPtr](../../atl/reference/ccomgitptr-class.md)|Этот класс предоставляет методы для обработки указателей интерфейса и глобальной таблицы интерфейсов (GIT).|atlbase.h|  
|[CComHeap](../../atl/reference/ccomheap-class.md)|Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции выделения памяти COM.|ATLComMem.h|  
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|Класс смарт-указатель для управления кучей указателей.|atlbase.h|  
|[CComModule](../../atl/reference/ccommodule-class.md)|По состоянию на ATL 7.0 `CComModule` является устаревшим: см. в разделе [модули ATL](../../atl/atl-module-classes.md) для получения дополнительных сведений.|atlbase.h|  
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|Этот класс предоставляет методы поточно ориентированные увеличивать и уменьшать значение переменной.|atlbase.h|  
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|Этот класс предоставляет методы поточно ориентированные увеличивать и уменьшать значение переменной без критический раздел блокировки или разблокировки функциональные возможности.|atlbase.h|  
|[CComObject](../../atl/reference/ccomobject-class.md)|Этот класс реализует `IUnknown` неагрегированные объекта.|atlcom.h|  
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|Этот класс управляет значение счетчика ссылок на модуль, содержащий ваш `Base` объекта.|atlcom.h|  
|[CComObjectNoLock](../../atl/reference/ccomobjectnolock-class.md)|Этот класс реализует `IUnknown` для неагрегированные объекта, но не не инкремента, счетчик блокировок модуля в конструкторе.|atlcom.h|  
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|Это определение типа из [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) шаблонизируется потоковая модель сервера по умолчанию.|atlcom.h|  
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|Этот класс предоставляет методы для обработки объекта управления счетчиками ссылок для объектов неагрегированные и объединены.|atlcom.h|  
|[CComObjectStack](../../atl/reference/ccomobjectstack-class.md)|Этот класс создает временный объект COM и предоставляет его с базовой реализацией `IUnknown`.|atlcom.h|  
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|Этот класс реализует `IUnknown` для суммирования или неагрегированные объекта.|atlcom.h|  
|[CComPtr](../../atl/reference/ccomptr-class.md)|Класс смарт-указатель для управления указателей интерфейса СОМ.|atlcomcli.h|  
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|Этот класс предоставляет основу для классов интеллектуальных указателей, использование памяти на основе COM-подпрограммы.|atlcomcli.h|  
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|Класс смарт-указатель для управления указателей интерфейса СОМ.|atlcomcli.h|  
|[CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекции указателей интерфейса СОМ.|atlcoll.h|  
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|Этот класс является оболочкой для `SAFEARRAY Data Type` структуры.|atlsafe.h|  
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|Этот класс является оболочкой для `SAFEARRAYBOUND` структуры.|atlsafe.h|  
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|Этот класс управляет выделения потока для класса [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).|atlbase.h|  
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|Этот класс предоставляет методы для увеличение и уменьшение значения переменной.|atlbase.h|  
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|Этот класс реализует интерфейс перемещаемой.|atlcom.h|  
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|В этом классе хранится `IUnknown` указатели и предназначен для использования в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класс шаблона.|atlcom.h|  
|[CComVariant](../../atl/reference/ccomvariant-class.md)|Этот класс заключает в оболочку тип VARIANT, предоставляя члена, указывающий тип данных, которые хранятся.|atlcomcli.h|  
|[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)|Этот класс реализует окно, содержатся внутри другого объекта.|atlwin.h|  
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|Этот класс предоставляет методы для управления памяти с помощью подпрограммы CRT памяти.|файле atlcore.h|  
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции кучи CRT.|atlmem.h|  
|[CDacl](../../atl/reference/cdacl-class.md)|Этот класс является оболочкой для структуры DACL (список управления доступом).|ATLSecurity.h|  
|[Класс CDebugReportHook](../../atl/reference/cdebugreporthook-class.md)|Этот класс используется для отправки отчетов отладки именованного канала.|файлов atlutil.h|  
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|Этот класс предоставляет два статических функций для преобразования символов в верхний или нижний регистр.|atlcoll.h|  
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|Этот класс предоставляет по умолчанию элемент функции сравнения.|atlcoll.h|  
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|Этот класс предоставляет функции и методы по умолчанию для класса коллекции.|atlcoll.h|  
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|Этот класс предоставляет статическую функцию для вычисления хэш-значения.|atlcoll.h|  
|[CDialogImpl](../../atl/reference/cdialogimpl-class.md)|Этот класс предоставляет методы для создания модальное или немодальное диалоговое окно.|atlwin.h|  
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|Этот класс предоставляет методы, поддержки динамической цепочки схемы сообщений.|atlwin.h|  
|[CElementTraits](../../atl/reference/celementtraits-class.md)|Этот класс используется классами коллекцию для предоставления методов и функций для перемещения, копирования, сравнения и операций хэширования.|atlcoll.h|  
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|Этот класс предоставляет копирования по умолчанию и переместить методы для класса коллекции.|atlcoll.h|  
|[CFirePropNotifyEvent](../../atl/reference/cfirepropnotifyevent-class.md)|Этот класс предоставляет методы для уведомления контейнера приемник об изменениях свойств элемента управления.|atlctl.h|  
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции глобального кучи Win32.|atlmem.h|  
|[CHandle](../../atl/reference/chandle-class.md)|Этот класс предоставляет методы для создания и использования объекта дескриптора.|atlbase.h|  
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|Класс смарт-указатель для управления кучей указателей.|файле atlcore.h|  
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|Этот класс — это основа для нескольких классов кучи смарт-указатель.|файле atlcore.h|  
|[Класс CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)|Этот класс предоставляет методы, статические функции и определения типов полезно при создании коллекций указателей кучи.|atlcoll.h|  
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|Этот класс предоставляет методы, используемые при построении списка указатели кучи.|atlcoll.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Предоставляет улучшенную поддержку растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).|atlimage.h|  
|[CInterfaceArray](../../atl/reference/cinterfacearray-class.md)|Этот класс предоставляет методы, используемые при создании массива указателей COM-интерфейса.|atlcoll.h|  
|[CInterfaceList](../../atl/reference/cinterfacelist-class.md)|Этот класс предоставляет методы, используемые при построении списка указателей интерфейса СОМ.|atlcoll.h|  
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций Win32 локальной куче.|atlmem.h|  
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|Этот класс позволяет получать доступ к другому объекту схемы сообщений объекта.|atlwin.h|  
|[Класс CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передают их в рабочий объект, который создается и уничтожается при каждом запросе.|файлов atlutil.h|  
|[Класс CNoWorkerThread](../../atl/reference/cnoworkerthread-class.md)|Этот класс используется в качестве аргумента для `MonitorClass` кэша параметров шаблона классов, если вы хотите отключить обслуживания динамического кэша.|файлов atlutil.h|  
|[Класс CPathT](../../atl/reference/cpatht-class.md)|Этот класс представляет собой путь.|atlpath.h|  
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|Этот класс предоставляет методы по умолчанию и функции для класса коллекции состоят из примитивных типов данных.|atlcoll.h|  
|[CPrivateObjectSecurityDesc](../../atl/reference/cprivateobjectsecuritydesc-class.md)|Этот класс представляет объект дескриптора безопасности закрытый объект.|ATLSecurity.h|  
|[CRBMap](../../atl/reference/crbmap-class.md)|Этот класс представляет структуру сопоставления, с помощью двоичного красно-черного дерева.|atlcoll.h|  
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|Этот класс представляет структуру сопоставления, которая позволяет каждого ключа должны быть сопоставлены более одного значения, с помощью двоичного красно-черного дерева.|atlcoll.h|  
|[CRBTree](../../atl/reference/crbtree-class.md)|Этот класс предоставляет методы для создания и использования красно-черного дерева.|atlcoll.h|  
|[CRegKey](../../atl/reference/cregkey-class.md)|Этот класс содержит методы для работы записей в системном реестре.|atlbase.h|  
|[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)|Этот класс предоставляет функции создания потока CRT. Этот класс используется в том случае, если поток будет использовать функции CRT.|atlbase.h|  
|[CSacl](../../atl/reference/csacl-class.md)|Этот класс является оболочкой для структуры системный список управления ДОСТУПОМ (системный список управления доступом).|ATLSecurity.h|  
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|Этот класс является тонкой оболочкой для `SECURITY_ATTRIBUTES` структуры.|ATLSecurity.h|  
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|Этот класс является оболочкой для `SECURITY_DESCRIPTOR` структуры.|ATLSecurity.h|  
|[CSid](../../atl/reference/csid-class.md)|Этот класс является оболочкой для `SID` структуры (идентификатором безопасности).|ATLSecurity.h|  
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|Этот класс предоставляет методы для управления простого массива.|atlsimpcoll.h|  
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|Этот класс представляет вспомогательный объект для [CSimpleArray](../../atl/reference/csimplearray-class.md) класса.|atlsimpcoll.h|  
|[CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)|Этот класс представляет вспомогательный объект для [CSimpleArray](../../atl/reference/csimplearray-class.md) класса.|atlsimpcoll.h|  
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|Этот класс реализует базовый модальное диалоговое окно.|atlwin.h|  
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|Этот класс обеспечивает поддержку для массива простое сопоставление.|atlsimpcoll.h|  
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|Этот класс представляет вспомогательный объект для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.|atlsimpcoll.h|  
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|Этот класс представляет вспомогательный объект для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.|atlsimpcoll.h|  
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|Этот класс предоставляет методы для реализации объект узла оснастки.|atlsnap.h|  
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|Этот класс предоставляет методы для реализации объект страницы свойств оснастки.|atlsnap.h|  
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|Этот класс предоставляет методы для поддержки стандартных свойств значения.|atlctl.h|  
|[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)|Этот класс предоставляет статические функции, используемые классами коллекцию хранения `CString` объектов.|CStringT.h|  
|[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)|Этот класс предоставляет статические функции, связанные с строк, которые хранятся в объектах класса коллекции. Это похоже на [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), но выполняет сравнение без учета регистра.|atlcoll.h|  
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|Этот класс предоставляет статические функции, связанные с строк, которые хранятся в объектах класса коллекции. Объекты-строки обрабатываются как ссылки.|atlcoll.h|  
|[Класс CThreadPool](../../atl/reference/cthreadpool-class.md)|Этот класс предоставляет пул рабочих потоков, обрабатывающих очередь рабочих элементов.|файлов atlutil.h|  
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|Этот класс является оболочкой для `TOKEN_GROUPS` структуры.|ATLSecurity.h|  
|[CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md)|Этот класс является оболочкой для `TOKEN_PRIVILEGES` структуры.|ATLSecurity.h|  
|[Класс CUrl](../../atl/reference/curl-class.md)|Этот класс представляет URL-адрес. Он позволяет управлять каждый элемент URL-адреса независимо от других ли синтаксический анализ URL-адрес существующей строки или создании строки с нуля.|файлов atlutil.h|  
|[CW2AEX](../../atl/reference/cw2aex-class.md)|Этот класс используется, макросы преобразования строк CT2AEX, CW2TEX, CW2CTEX и CT2CAEX и typedef CW2A.|atlconv.h|  
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|Этот класс используется, макросы преобразования строк CW2CTEX CT2CWEX и typedef CW2CW.|atlconv.h|  
|[CW2WEX](../../atl/reference/cw2wex-class.md)|Этот класс используется, макросы преобразования строк CW2TEX CT2WEX и typedef CW2W.|atlconv.h|  
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.|atlmem.h|  
|[CWindow](../../atl/reference/cwindow-class.md)|Этот класс предоставляет методы для управления окном.|atlwin.h|  
|[CWindowImpl](../../atl/reference/cwindowimpl-class.md)|Этот класс предоставляет методы для создания или создание подкласса для окна.|atlwin.h|  
|[CWinTraits](../../atl/reference/cwintraits-class.md)|Этот класс предоставляет метод для стандартизации стилей, которые используются при создании объекта окна.|atlwin.h|  
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|Этот класс предоставляет метод для стандартизации стилей, которые используются при создании объекта окна.|atlwin.h|  
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|Этот класс предоставляет методы для регистрации сведений о для класса окна.|atlwin.h|  
|[Класс CWorkerThread](../../atl/reference/cworkerthread-class.md)|Этот класс создает рабочий поток или используется существующая рабочая область, ожидает один или несколько дескрипторов объектов ядра и выполняет функцию указанного клиента, когда один из маркеров, получает сигнал.|файлов atlutil.h|  
|[IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)|Этот класс представляет интерфейс для `CreateInstance` метод.|atlbase.h|  
|[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)|Этот класс представляет интерфейс для диспетчера памяти.|atlmem.h|  
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|Этот интерфейс предоставляет методы для определения характеристик размещаемого элемента управления или контейнера.|atlbase.h, насколько|  
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|Этот интерфейс реализует Дополнительные внешние свойства для размещаемого элемента управления.|atlbase.h, насколько|  
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|Этот интерфейс содержит методы для работы элемента управления и его объект узла.|atlbase.h, насколько|  
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|Этот интерфейс предоставляет методы для управления лицензированный элемент управления и его объект узла.|atlbase.h, насколько|  
|[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)|Этот класс предоставляет методы, используемые классом коллекции.|atlcom.h|  
|[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)|Этот класс реализует контейнер точек соединения, чтобы управлять коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов.|atlcom.h|  
|[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)|Этот класс реализует точку соединения.|atlcom.h|  
|[IDataObjectImpl](../../atl/reference/idataobjectimpl-class.md)|Этот класс предоставляет методы для поддержки унифицированная передача данных и управление подключениями.|atlctl.h|  
|[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)|Этот класс предоставляет реализацию по умолчанию для `IDispatch` часть сдвоенный интерфейс.|atlcom.h|  
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|Этот класс предоставляет реализацию `IDispatch` методы.|atlcom.h|  
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|Этот класс предоставляет реализацию `IDispatch` методы без получения сведений о типе из библиотеки типов.|atlcom.h|  
|[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)|Интерфейс для синтаксического анализа Microsoft HTML и механизм визуализации.|atlbase.h, насколько|  
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|Этот класс определяет перечислитель интерфейс на основе коллекции стандартной библиотеки C++.|atlcom.h|  
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|Этот класс предоставляет реализацию по умолчанию `IObjectSafety` интерфейс, позволяющий клиенту получить и задать уровни безопасности объекта.|atlctl.h|  
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|Этот класс предоставляет методы, что объект, для взаимодействия со своим сайтом.|atlcom.h|  
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|Этот класс предоставляет реализацию по умолчанию `IOleControl` интерфейса и реализует `IUnknown`.|atlctl.h|  
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|Этот класс предоставляет методы, за помощь при написании связи между элементом управления на месте и его контейнером.|atlctl.h|  
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|Этот класс реализует `IUnknown` и предоставляет методы, позволяющие безоконный элемент управления для получения оконных сообщений и принять участие в операциях перетаскивания и вставки.|atlctl.h|  
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|Этот класс реализует `IUnknown` и — это основной интерфейс, через который контейнер взаимодействует с элементом управления.|atlctl.h|  
|[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)|Этот класс реализует `IUnknown` и позволяет клиенту получать доступ к сведениям на страницах свойств объекта.|atlctl.h|  
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|Этот класс реализует `IUnknown` и позволяет сохранить его свойства в контейнер свойств, предоставляемых клиентом объекту.|atlcom.h|  
|[IPersistStorageImpl](../../atl/reference/ipersiststorageimpl-class.md)|Этот класс реализует [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) интерфейс.|atlcom.h|  
|[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)|Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) интерфейс.|atlcom.h|  
|[IPointerInactiveImpl](../../atl/reference/ipointerinactiveimpl-class.md)|Этот класс реализует `IUnknown` и [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) методы интерфейса.|atlctl.h|  
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|Этот класс предоставляет [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс как исходящий интерфейс в подключаемом объекте.|atlctl.h|  
|[IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)|Этот класс реализует `IUnknown` и наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).|atlctl.h|  
|[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)|Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) интерфейс.|atlctl.h|  
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|Этот класс предоставляет реализацию по умолчанию [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) и [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) методы.|atlcom.h|  
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|Этот класс объединяет инициализации элемента управления контейнеры в один вызов.|atlctl.h|  
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) интерфейс.|atlctl.h|  
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|Этот класс предоставляет реализацию по умолчанию `IServiceProvider` интерфейс.|atlcom.h|  
|[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)|Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) интерфейс.|atlcom.h|  
|[ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md)|Этот класс предоставляет реализацию по умолчанию `ISupportErrorInfo Interface` интерфейс и может использоваться, когда только один интерфейс выдает ошибки для объекта.|atlcom.h|  
|[Интерфейс IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)|Этот интерфейс предоставляет методы для настройки пула потоков.|файлов atlutil.h|  
|[IViewObjectExImpl](../../atl/reference/iviewobjecteximpl-class.md)|Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), и [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) интерфейсов.|atlctl.h|  
|[Интерфейс IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient` — Это интерфейс, реализуемый клиентами [CWorkerThread](../../atl/reference/cworkerthread-class.md) класса.|файлов atlutil.h|  
|[_U_MENUorID](../../atl/reference/u-menuorid-class.md)|Этот класс предоставляет оболочки для `CreateWindow` и `CreateWindowEx`.|atlwin.h|  
|[_U_RECT](../../atl/reference/u-rect-class.md)|Предоставляет класс адаптера этот аргумент `RECT` указатели или ссылки, должны быть переданы функции, которая реализуется в терминах указатели.|atlwin.h|  
|[_U_STRINGorID](../../atl/reference/u-stringorid-class.md)|Этот класс адаптера аргумент позволяет имена ресурсов (LPCTSTRs) или идентификаторы ресурсов (единицы), должны быть переданы функции, не требуя вызывающий объект, преобразуемый в строку с помощью макроса MAKEINTRESOURCE идентификатор.|atlwin.h|  
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|Этот класс предоставляет функции создания для потока Windows. Этот класс используется в том случае, если поток не будет использовать функции CRT.|atlbase.h|  
  
## <a name="see-also"></a>См. также  
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)   
 [Функции](../../atl/reference/atl-functions.md)   
 [Глобальные переменные](../../atl/reference/atl-global-variables.md)   
 [Определения типов](../../atl/reference/atl-typedefs.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)


