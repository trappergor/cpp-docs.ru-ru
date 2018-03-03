---
title: "Элементы управления ActiveX MFC: Сериализация | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34b8f0520d1f071bb408f782b0f2370ef29f528e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-serializing"></a>Элементы управления ActiveX в MFC. Сериализация
В этой статье описывается, как для сериализации элемента управления ActiveX. Сериализация — это процесс чтение или запись на носитель постоянное хранилище, например файл на диске. Библиотека Microsoft Foundation Class (MFC) предоставляет встроенную поддержку сериализации в классе `CObject`. `COleControl`расширяет эту функцию на элементы управления ActiveX с помощью механизма обмена свойство.  
  
 Сериализация для элементов управления ActiveX реализуется путем переопределения [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Эта функция вызывается во время загрузки и сохранения объект управления хранит все свойства, реализуемые с переменной-члена или переменную-член с уведомления об изменениях.  
  
 Основные проблемы, связанные с сериализации элемента управления ActiveX, рассматриваются в следующих разделах:  
  
-   Реализация `DoPropExchange` для сериализации объекта управления  
  
-   [Настройка процесса сериализации](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [Реализация поддержки версии](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a>Для реализации функции DoPropExchange  
 При использовании мастера элементов управления ActiveX для создания проекта элемента управления, несколько функций обработчик по умолчанию автоматически добавляются в класс элемента управления, включая реализацию по умолчанию [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). В примере показан код, добавленный к классам, созданных с помощью мастера элементов управления ActiveX:  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]  
  
 Если вы хотите сделать свойство постоянные, изменить `DoPropExchange` путем добавления вызова функции exchange свойство. В следующем примере демонстрируется сериализация пользовательского свойства типа Boolean CircleShape, где свойство CircleShape имеет значение по умолчанию **TRUE**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]  
  
 В следующей таблице перечислены функции обмена возможные свойства, которые можно использовать для сериализации свойств элемента управления:  
  
|Функции обмена данными свойство|Цель|  
|---------------------------------|-------------|  
|**PX_Blob)**|Сериализует тип данных свойства больших двоичных объектов (BLOB).|  
|**PX_Bool)**|Сериализует тип свойства типа Boolean.|  
|**PX_Color)**|Сериализует свойство цвета типа.|  
|**PX_Currency)**|Сериализует тип **CY** свойство (currency).|  
|**PX_Double)**|Сериализует тип **двойные** свойство.|  
|**PX_Font)**|Сериализует свойство типа шрифта.|  
|**PX_Float)**|Сериализует тип **float** свойство.|  
|**PX_IUnknown)**|Сериализует свойства типа `LPUNKNOWN`.|  
|**PX_Long)**|Сериализует тип **длинные** свойство.|  
|**PX_Picture)**|Сериализует тип свойства изображения.|  
|**PX_Short)**|Сериализует тип **короткие** свойство.|  
|**(PXstring)**|Сериализует тип `CString` свойства.|  
|**PX_ULong)**|Сериализует тип **ULONG** свойство.|  
|**PX_UShort)**|Сериализует тип **USHORT** свойство.|  
  
 Дополнительные сведения об этих функциях свойства exchange см. в разделе [сохраняемости OLE элементов управления](../mfc/reference/persistence-of-ole-controls.md) в *Справочник по библиотеке MFC*.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>Настройка поведения по умолчанию DoPropExchange  
 Реализация по умолчанию **DoPropertyExchange** (как показано в предыдущем разделе) вызывает метод базового класса `COleControl`. Это сериализует набор свойств, автоматически поддерживаемые `COleControl`, которая использует больше места, чем сериализации только пользовательские свойства элемента управления. Удаление этого вызова позволяет объекта для сериализации только свойств, которую вы считаете важной. Все состояния стандартное свойство реализации элемента управления не будут сериализованы при сохранении или загрузке объект элемента управления, можно явно добавить **PX_** вызывает для них.  
  
##  <a name="_core_implementing_version_support"></a>Реализация поддержки версии  
 Поддержка версий позволяет измененный элемент ActiveX для добавления новых свойств постоянных и по-прежнему сможет обнаружить и загрузить постоянное состояние, созданные в более ранней версии элемента управления. Чтобы изменить версию элемента управления в рамках постоянные данные, вызовите [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) в элементе управления `DoPropExchange` функции. Этот вызов будет автоматически вставлен, если элемент управления ActiveX был создан с помощью мастера элементов управления ActiveX. Можно удалить, если не требуется поддержка версий. Тем не менее, размер элемента управления обходится очень мелкий (4 байта) для более гибкие, обеспечивающий поддержку версии.  
  
 Если элемент управления не была создана с помощью мастера элементов управления ActiveX, добавьте вызов `COleControl::ExchangeVersion` , вставив следующую строку в начале вашей `DoPropExchange` функции (перед вызовом `COleControl::DoPropExchange`):  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Можно использовать любой `DWORD` как номер версии. Проекты, созданные с помощью мастера элементов управления ActiveX используют **_wVerMinor** и **_wVerMajor** по умолчанию. Это глобальные константы, определенные в файле реализации класса элемента управления ActiveX проекта. В оставшейся части вашего `DoPropExchange` функции, можно вызвать [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) в любой момент извлечь версию сохранения или получения.  
  
 В следующем примере версии 1 Этот пример элемента управления имеет только свойство «ReleaseDate». Версия 2 добавляет свойство «OriginalDate». Если элемент управления настраивается для загрузки из старой версии постоянное состояние, она инициализирует переменную-член для нового свойства, значение по умолчанию.  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 По умолчанию элемент управления «преобразует» старые данные в формате последней версии. Например если элемент управления версии 2 загружает данные, которые были сохранены в версии 1, напишете формат версии 2 при его сохранении еще раз. Если требуется элемент управления для сохранения данных в формате последний считанный передать **FALSE** качестве третьего параметра при вызове `ExchangeVersion`. Это третий параметр является необязательным и используется **TRUE** по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

