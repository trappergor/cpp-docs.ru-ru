---
title: Делегат и интерфейс Карта Макрос (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: e08597d024f5e3a74dcf47363ad3de0aa60cf6c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365827"
---
# <a name="delegate-and-interface-map-macros"></a>Макросы схем делегата и интерфейса

MFC поддерживает эти макросы для карт делегатов и интерфейсов:

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Начинается карта делегата.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Начинается определение свисохой карты.|
|[Делегат CommandHandler](#commandhandler)|Регистрирует методы обратного вызова с помощью источника команды.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Завершает карту делегата.|
|[END_INTERFACE_MAP](#end_interface_map)|Завершает карту интерфейса в файле реализации. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Создает запись на карте делегата.|
|[INTERFACE_PART](#interface_part)|Используется между BEGIN_INTERFACE_MAP макросом и END_INTERFACE_MAP макросом для каждого интерфейса, который будет поддерживаться объектом.|
|[MAKE_DELEGATE](#make_delegate)|Прикрепляет обработчик событий к управляемому управлению.|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP

Начинается карта делегата.

### <a name="syntax"></a>Синтаксис

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>Параметры

*Класса*<br/>
Класс, в котором размещается управляемый элемент управления.

### <a name="remarks"></a>Remarks

Этот макрос знаменует собой начало списка записей делегатов, которые составляют карту делегата. На примере использования этого макроса см. [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Требования

**Заголовок:** msclr'event.h

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

Начинаетопределение сотилийной карты при использовании в файле реализации.

### <a name="syntax"></a>Синтаксис

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Класс, в котором определяется схема интерфейсов.

*базовыйКласс*<br/>
Класс, из которого происходит *Class.*

### <a name="remarks"></a>Remarks

Для каждого реализованного интерфейса имеется один или несколько INTERFACE_PART макровызовов. Для каждого агрегата, который использует класс, есть один INTERFACE_AGGREGATE макровызов.

Для получения дополнительной информации о интерфейсных картах [см.](../tn038-mfc-ole-iunknown-implementation.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a>Делегат командования

Регистрирует методы обратного вызова с помощью источника команды.

### <a name="syntax"></a>Синтаксис

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

### <a name="remarks"></a>Remarks

Этот делегат регистрирует методы обратного вызова с помощью источника команд. При добавлении делегата к объекту исходного кода команды метод обратного вызова становится обработчиком для команд, поступающих из указанного источника.

Для получения дополнительной информации [см. Как: Добавьте командную расшатывание в управление формами Windows.](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определяется в сборке atlmfc-lib'mfcmifc80.dll)

## <a name="commanduihandler"></a><a name="commanduihandler"></a>КомандойИДлер

Регистрирует методы обратного вызова с помощью сообщения команды обновления пользовательского интерфейса.

### <a name="syntax"></a>Синтаксис

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

*cmdUI*<br/>
Идентификатор идентификатор сообщения команды.

### <a name="remarks"></a>Remarks

Этот делегат регистрирует методы обратного вызова с помощью командного сообщения об обновлении пользовательского интерфейса. `CommandUIHandler`похож на [CommandHandler,](#commandhandler) за исключением того, что этот делегат используется с командами обновления объектов пользовательского интерфейса. Команды обновления пользовательского интерфейса должны быть отображены один к одному с методами обработчика сообщений.

Для получения дополнительной информации об использовании форм Windows, [см.](../../dotnet/using-a-windows-form-user-control-in-mfc.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определяется в сборке atlmfc-lib'mfcmifc80.dll)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a>END_DELEGATE_MAP

Завершает карту делегата.

### <a name="syntax"></a>Синтаксис

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>Remarks

Этот макрос знаменует собой конец списка записей делегатов, которые составляют карту делегата. На примере использования этого макроса см. [EVENT_DELEGATE_ENTRY](#event_delegate_entry).

### <a name="requirements"></a>Требования

**Заголовок:** msclr'event.h

## <a name="end_interface_map"></a><a name="end_interface_map"></a>END_INTERFACE_MAP

Завершает карту интерфейса в файле реализации.

### <a name="syntax"></a>Синтаксис

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о картах интерфейсов [см.](../tn038-mfc-ole-iunknown-implementation.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

Создает запись на карте делегата.

### <a name="syntax"></a>Синтаксис

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>Параметры

*Член*<br/>
Метод обработчика событий, который должен быть прикреплен к элементу управления.

*ARG0*<br/>
Первый аргумент метода обработчика `Object^`управляемых событий, например.

*ARG1*<br/>
Второй аргумент метода обработчика `EventArgs^`управляемых событий, например.

### <a name="remarks"></a>Remarks

Каждая запись на карте делегата соответствует делегату обработчика управляемых событий, созданному [MAKE_DELEGATE.](#make_delegate)

### <a name="example"></a>Пример

Следующий пример кода показывает, как использовать EVENT_DELEGATE_ENTRY для создания `OnClick` записи на карте делегата для обработчика событий; также смотрите пример кода в MAKE_DELEGATE. Для получения дополнительной информации [см. Как: Sink Windows Формы События из родных классов C .](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** msclr'event.h

## <a name="interface_part"></a><a name="interface_part"></a>INTERFACE_PART

Используется между BEGIN_INTERFACE_MAP макросом и END_INTERFACE_MAP макросом для каждого интерфейса, который будет поддерживаться объектом.

### <a name="syntax"></a>Синтаксис

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса, содержащего схему интерфейсов.
*Iid*<br/>
IID, который должен быть отображен на встроенный класс.
*локальныйКласс*<br/>
Название местного класса.

### <a name="remarks"></a>Remarks

Это позволяет сопоставить IID с членом класса, указанным *Class* и *localClass.*

Для получения дополнительной информации о интерфейсных картах [см.](../tn038-mfc-ole-iunknown-implementation.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="make_delegate"></a><a name="make_delegate"></a>MAKE_DELEGATE

Прикрепляет обработчик событий к управляемому управлению.

### <a name="syntax"></a>Синтаксис

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>Параметры

*Делегат*<br/>
Тип делегата обработчика управляемых событий, например [EventHandler.](/dotnet/api/system.eventhandler)

*Член*<br/>
Название метода обработчика событий, который будет прикреплен к элементу управления.

### <a name="remarks"></a>Remarks

Этот макрос создает делегата обработчика управляемых событий типа *DELEGATE* и имени *MEMBER.* Делегат обработчика управляемых событий позволяет родному классу обрабатывать управляемые события.

### <a name="example"></a>Пример

В следующем примере кода `MAKE_DELEGATE` показано, `OnClick` как вызвать для `MyControl`прикрепления обработчика событий к управлению MFC. Более широкое объяснение того, как этот макрос работает в приложении MFC, [см.](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** msclr'event.h

## <a name="see-also"></a>См. также раздел

[Практическое руководство. Получение событий Windows Forms из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
