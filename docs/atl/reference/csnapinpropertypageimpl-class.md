---
title: Класс CSnapInPropertyPageImpl
ms.date: 11/04/2016
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
ms.openlocfilehash: d4e363f7de46de6f875a28a62d4ecdf929decdc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272182"
---
# <a name="csnapinpropertypageimpl-class"></a>Класс CSnapInPropertyPageImpl

Этот класс предоставляет методы для реализации объект страницы свойств оснастки.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Изменяет состояние **ОК** и **отменить** кнопки.|
|[CSnapInPropertyPageImpl::Create](#create)|Инициализирует только что созданный объект `CSnapInPropertyPageImpl` объекта.|
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Вызывается платформой, когда пользователь щелкает **применить** кнопки при использовании листа свойств мастера.|
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Вызывается платформой, когда пользователь щелкает **помочь** кнопки при использовании листа свойств мастера.|
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Вызывается платформой, когда текущая страница больше не активна.|
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Вызывается платформой, когда пользователь щелкает **отменить** кнопку и до отмены.|
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Вызывается платформой, когда пользователь щелкает **Сброс** кнопки при использовании листа свойств мастера.|
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Вызывается платформой, когда текущая страница становится активным.|
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Вызывается платформой, когда пользователь щелкает **обратно** кнопки при использовании листа свойств мастера.|
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Вызывается платформой, когда пользователь щелкает **Готово** кнопки при использовании листа свойств мастера.|
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Вызывается платформой, когда пользователь щелкает **Далее** кнопки при использовании листа свойств мастера.|
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Перенаправляет текущее сообщение для всех страниц свойств.|
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Вызов, активация и деактивация **применить** кнопки.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows `PROPSHEETPAGE` структуру, используемую `CSnapInPropertyPageImpl` объекта.|

## <a name="remarks"></a>Примечания

`CSnapInPropertyPageImpl` Предоставляет базовую реализацию для объекта оснастки свойства страницы. Основные возможности страницы свойств – – оснастка реализуются с помощью нескольких различных интерфейсов и сопоставления типов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsnap.h

##  <a name="canceltoclose"></a>  CSnapInPropertyPageImpl::CancelToClose

Вызывайте эту функцию после неустранимой изменения данных на странице модальную страницу свойств.

```
void CancelToClose();
```

### <a name="remarks"></a>Примечания

Эта функция приведет к изменению **ОК** кнопки **закрыть** и отключить **отменить** кнопки. Это изменение оповещений, которые пользователь, что изменение не постоянной, а изменения не может быть отменено.

`CancelToClose` Функция-член ничего не делает в немодальный лист свойств, так как нет безмодальной вкладки свойства **отменить** кнопку по умолчанию.

##  <a name="csnapinpropertypageimpl"></a>  CSnapInPropertyPageImpl::CSnapInPropertyPageImpl

Создает объект `CSnapInPropertyPageImpl`.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>Параметры

*lpszTitle*<br/>
[in] Заголовок страницы свойств.

### <a name="remarks"></a>Примечания

Чтобы инициализировать базовой структуры, вызовите [CSnapInPropertyPageImpl::Create](#create).

##  <a name="create"></a>  CSnapInPropertyPageImpl::Create

Вызывайте эту функцию для инициализации структуры страницы свойств.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор `PROPSHEETPAGE` структуру, содержащую атрибуты листа созданное свойство.

### <a name="remarks"></a>Примечания

Сначала следует вызвать [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) перед вызовом этой функции.

##  <a name="m_psp"></a>  CSnapInPropertyPageImpl::m_psp

`m_psp` — это структура, члены которой хранения характеристики `PROPSHEETPAGE`.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Примечания

Эта структура используется для инициализации внешний вид страницы свойств после его создания.

Дополнительные сведения об этой структуре, включая список его элементов, см. в разделе [PROPSHEETPAGE](https://msdn.microsoft.com/library/aa815151) в пакете Windows SDK.

##  <a name="onapply"></a>  CSnapInPropertyPageImpl::OnApply

Эта функция-член вызывается, когда пользователь щелкает **ОК** или **применить** кнопки.

```
BOOL OnApply();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если изменения принимаются; в противном случае 0.

### <a name="remarks"></a>Примечания

Прежде чем `OnApply` может вызываться платформой, вам необходимо вызвать метод `SetModified` и задайте для его параметра значение true. Это активирует **применить** кнопку сразу же после внесения изменений на странице свойств.

Переопределить эта функция-член для указания принимает программы, когда пользователь щелкает **применить** кнопки. При переопределении метода, данная функция должна возвращать значение TRUE, чтобы принять изменения и значение FALSE, чтобы предотвратить изменения вступают в силу.

Реализация по умолчанию `OnApply` возвращает значение TRUE.

##  <a name="onhelp"></a>  CSnapInPropertyPageImpl::OnHelp

Эта функция-член вызывается, когда пользователь щелкает **помочь** кнопку на странице свойств.

```
void OnHelp();
```

### <a name="remarks"></a>Примечания

Переопределите эта функция-член для отображения справки для страницы свойств.

##  <a name="onkillactive"></a>  CSnapInPropertyPageImpl::OnKillActive

Эта функция-член вызывается в том случае, когда страница перестает быть активной страницей.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если данных был успешно обновлен; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределите эта функция-член для выполнения задач проверки специальных данных.

##  <a name="onquerycancel"></a>  CSnapInPropertyPageImpl::OnQueryCancel

Эта функция-член вызывается, когда пользователь щелкает **отменить** кнопку и перед "Отмена" было выполнено действие.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, чтобы разрешить операцию "Отмена"; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределить эта функция-член для указания программа принимает, когда пользователь щелкает действие **отменить** кнопки.

Реализация по умолчанию `OnQueryCancel` возвращает значение TRUE.

##  <a name="onreset"></a>  CSnapInPropertyPageImpl::OnReset

Эта функция-член вызывается, когда пользователь щелкает **отменить** кнопки.

```
void OnReset();
```

### <a name="remarks"></a>Примечания

При вызове этой функцией, изменяется на все страницы свойств, выполненные ранее нажатие пользователем **применить** кнопку пропускаются, и окно свойств сохраняет фокус.

Переопределить эта функция-член для указания программа принимает, когда пользователь щелкает **отменить** кнопки.

##  <a name="onsetactive"></a>  CSnapInPropertyPageImpl::OnSetActive

Эта функция-член вызывается в том случае, когда страница, выбранный пользователем и становится активной страницей.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если страницы был успешно задан активно; в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределение для выполнения задач, когда страница активируется эта функция-член. Переопределенный эта функция-член следует вызвать версию по умолчанию, перед выполнением других обработки.

Реализация по умолчанию возвращает значение TRUE.

##  <a name="onwizardback"></a>  CSnapInPropertyPageImpl::OnWizardBack

Эта функция-член вызывается, когда пользователь щелкает **обратно** кнопки с помощью мастера.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Возвращаемое значение

- 0, чтобы автоматически перейти на предыдущую страницу.

- значение -1, чтобы предотвратить изменение страницы.

Чтобы перейти на страницу, отличном от того, далее, возвращают идентификатор для отображения диалогового окна.

### <a name="remarks"></a>Примечания

Переопределить эта функция-член для указания некоторых операций, когда должен выполнить пользователь **обратно** кнопки.

##  <a name="onwizardfinish"></a>  CSnapInPropertyPageImpl::OnWizardFinish

Эта функция-член вызывается, когда пользователь щелкает **Готово** кнопки с помощью мастера.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если окно свойств уничтожается после завершения работы мастера; в противном случае значение равно нулю.

### <a name="remarks"></a>Примечания

Переопределить эта функция-член для указания некоторых операций, когда должен выполнить пользователь **Готово** кнопки.

##  <a name="onwizardnext"></a>  CSnapInPropertyPageImpl::OnWizardNext

Эта функция-член вызывается, когда пользователь щелкает **Далее** кнопки с помощью мастера.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Возвращаемое значение

- 0, чтобы автоматически перейти на следующую страницу.

- значение -1, чтобы предотвратить изменение страницы.

Чтобы перейти на страницу, отличном от того, далее, возвращают идентификатор для отображения диалогового окна.

### <a name="remarks"></a>Примечания

Переопределить эта функция-член для указания некоторых операций, когда должен выполнить пользователь **Далее** кнопки.

##  <a name="querysiblings"></a>  CSnapInPropertyPageImpl::QuerySiblings

Вызовите эту функцию-член для пересылки сообщения для каждой страницы в окне свойств.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
[in] Указывает Дополнительные сведения, зависящие от сообщения.

*lParam*<br/>
[in] Указывает Дополнительные сведения, зависящие от сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение не должно быть перенаправлено на следующую страницу свойств; в противном случае значение равно нулю.

### <a name="remarks"></a>Примечания

Если страница возвращает ненулевое значение, окно свойств не отправляет сообщение на последующих страницах.

##  <a name="setmodified"></a>  CSnapInPropertyPageImpl::SetModified

Вызовите эту функцию-член для включения или отключения **применить** кнопки, в зависимости от того, следует ли применять параметры на странице свойств в соответствующий внешний объект.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Параметры

*bChanged*<br/>
[in] Значение TRUE указывает, что параметрах страницы свойств были изменены с момента последнего они были применены; Значение FALSE, чтобы указать, что были применены параметры страницы, или следует игнорировать.

### <a name="remarks"></a>Примечания

Окно свойств сохраняет записи, из которых страницы являются «грязный», то есть, страницы свойств, для которых вы вызвали `SetModified( TRUE )`. **Применить** всегда активируется кнопка при вызове метода `SetModified( TRUE )` для одной из страниц. **Применить** кнопка будет отключена при вызове `SetModified( FALSE )` для одной из страниц, но только если ни один из других страниц «грязный».

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
