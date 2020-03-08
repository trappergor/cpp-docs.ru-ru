---
title: Класс CPropertyPage
ms.date: 11/04/2016
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
ms.openlocfilehash: 6a6223708c83f7a5b3e6532a2016660d558f8270
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865435"
---
# <a name="cpropertypage-class"></a>Класс CPropertyPage

Представляет отдельные страницы вкладки свойств, также известные как диалоговое окно вкладки.

## <a name="syntax"></a>Синтаксис

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CPropertyPage:: CPropertyPage](#cpropertypage)|Формирует объект `CPropertyPage`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CPropertyPage:: Канцелтоклосе](#canceltoclose)|Изменяет кнопку "ОК" на "чтение закрыта" и отключает кнопку "Отмена" после неустранимого изменения на странице модальной страницы свойств.|
|[CPropertyPage:: конструкция](#construct)|Формирует объект `CPropertyPage`. Используйте `Construct`, если необходимо указать параметры во время выполнения или если используются массивы.|
|[CPropertyPage:: Жетпсп](#getpsp)|Извлекает структуру [Пропшитпаже](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) Windows, связанную с объектом `CPropertyPage`.|
|[CPropertyPage:: OnApply](#onapply)|Вызывается структурой при нажатии кнопки "Применить".|
|[CPropertyPage:: OnCancel](#oncancel)|Вызывается структурой при нажатии кнопки "Отмена".|
|[CPropertyPage:: Онкиллактиве](#onkillactive)|Вызывается структурой, когда текущая страница больше не является активной страницей. Проведите проверку данных здесь.|
|[CPropertyPage:: ОНОК](#onok)|Вызывается структурой при нажатии кнопки ОК, применить сейчас или закрыть.|
|[CPropertyPage:: OnQueryCancel](#onquerycancel)|Вызывается структурой при нажатии кнопки "Отмена" и до отмены.|
|[CPropertyPage:: OnReset](#onreset)|Вызывается структурой при нажатии кнопки "Отмена".|
|[CPropertyPage:: Онсетактиве](#onsetactive)|Вызывается структурой при выполнении страницы активной страницы.|
|[CPropertyPage:: Онвизардбакк](#onwizardback)|Вызывается структурой при нажатии кнопки "назад" при использовании страницы свойств типа мастера.|
|[CPropertyPage:: Онвизардфиниш](#onwizardfinish)|Вызывается структурой при нажатии кнопки "Готово" при использовании страницы свойств типа мастера.|
|[CPropertyPage:: Онвизарднекст](#onwizardnext)|Вызывается структурой при нажатии кнопки "Далее" при использовании страницы свойств типа мастера.|
|[CPropertyPage:: Куерисиблингс](#querysiblings)|Перенаправляет сообщение на каждую страницу страницы свойств.|
|[CPropertyPage:: SetModified](#setmodified)|Вызовите, чтобы активировать или деактивировать кнопку Применить сейчас.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[CPropertyPage:: m_psp](#m_psp)|Структура [Пропшитпаже](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) Windows. Предоставляет доступ к базовым параметрам страницы свойств.|

## <a name="remarks"></a>Remarks

Как и в случае со стандартными диалоговыми окнами, класс является производным от `CPropertyPage` для каждой страницы в странице свойств. Чтобы использовать объекты, производные от `CPropertyPage`, сначала создайте объект [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) , а затем создайте объект для каждой страницы, которая помещается на странице свойств. Вызовите [CPropertySheet:: addPage](../../mfc/reference/cpropertysheet-class.md#addpage) для каждой страницы на листе, а затем откройте страницу свойств, вызвав [CPropertySheet::D омодал](../../mfc/reference/cpropertysheet-class.md#domodal) для модальной страницы свойств или [CPropertySheet:: Create](../../mfc/reference/cpropertysheet-class.md#create) для немодальной страницы свойств.

Можно создать диалоговое окно типа «вкладка», которое состоит из страницы свойств с последовательностью страниц свойств, которые позволяют пользователю выполнить шаги операции, такие как Настройка устройства или создание информационного бюллетеня. В диалоговом окне Вкладка «тип мастера» страницы свойств не имеют вкладок и только одна страница свойств видна за раз. Кроме того, вместо того, чтобы применять кнопки "ОК" и "Применить", в диалоговом окне "Вкладка типа" есть кнопка "назад", кнопка "Далее" или "Готово" и кнопка "Отмена".

Дополнительные сведения о создании страницы свойств в качестве мастера см. в разделе [CPropertySheet:: сетвизардмоде](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Дополнительные сведения об использовании `CPropertyPage` объектов см. в статьях [свойств и страниц свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md)статьи.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>Требования

**Заголовок:** афксдлгс. h

##  <a name="canceltoclose"></a>CPropertyPage:: Канцелтоклосе

Вызовите эту функцию после внесения неустранимых изменений в данные на странице модальной страницы свойств.

```
void CancelToClose();
```

### <a name="remarks"></a>Remarks

Эта функция изменит кнопку ОК, чтобы закрыть и отключить кнопку Отмена. Это изменение предупреждает пользователя о том, что изменение является постоянным, и изменения не могут быть отменены.

Функция-член `CancelToClose` ничего не делает на немодальной странице свойств, так как немодальная страница свойств по умолчанию не имеет кнопки отмены.

### <a name="example"></a>Пример

  См. пример для [CPropertyPage:: куерисиблингс](#querysiblings).

##  <a name="construct"></a>CPropertyPage:: конструкция

Вызовите эту функцию-член для создания объекта `CPropertyPage`.

```
void Construct(
    UINT nIDTemplate,
    UINT nIDCaption = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0);

void Construct(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);
```

### <a name="parameters"></a>Параметры

*нидтемплате*<br/>
Идентификатор шаблона, используемого для этой страницы.

*нидкаптион*<br/>
Идентификатор имени, которое будет размещено на вкладке этой страницы. Если значение равно 0, то имя будет взято из шаблона диалогового окна для этой страницы.

*лпсзтемплатенаме*<br/>
Содержит строку, завершающуюся нулем, которая является именем ресурса шаблона.

*нидхеадертитле*<br/>
Идентификатор имени для размещения в заголовке заголовка страницы свойств. По умолчанию 0.

*нидхеадерсубтитле*<br/>
Идентификатор имени, помещаемого в расположение подзаголовка заголовка страницы свойств. По умолчанию 0.

### <a name="remarks"></a>Remarks

Объект отображается после выполнения всех следующих условий.

- Страница была добавлена в страницу свойств с помощью [CPropertySheet:: addPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Вызвана функция [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [CREATE](../../mfc/reference/cpropertysheet-class.md#create) на странице свойств.

- Пользователь выбрал эту страницу (с вкладками).

Вызовите `Construct`, если не был вызван один из других конструкторов класса. Функция-член `Construct` является гибкой, поскольку можно оставить Оператор Parameter пустым, а затем указать несколько параметров и конструкцию в любой точке кода.

При работе с массивами необходимо использовать `Construct`, и необходимо вызвать `Construct` для каждого элемента массива, чтобы членам данных были назначены правильные значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>CPropertyPage:: CPropertyPage

Формирует объект `CPropertyPage`.

```
CPropertyPage();

explicit CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

explicit CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```

### <a name="parameters"></a>Параметры

*нидтемплате*<br/>
Идентификатор шаблона, используемого для этой страницы.

*нидкаптион*<br/>
Идентификатор имени, которое будет размещено на вкладке этой страницы. Если значение равно 0, то имя будет взято из шаблона диалогового окна для этой страницы.

*двсизе*<br/>
*лпсзтемплатенаме* Указывает на строку, содержащую имя шаблона для этой страницы. Не может быть NULL.

*нидхеадертитле*<br/>
Идентификатор имени для размещения в заголовке заголовка страницы свойств.

*нидхеадерсубтитле*<br/>
Идентификатор имени, помещаемого в расположение подзаголовка заголовка страницы свойств.

### <a name="remarks"></a>Remarks

Объект отображается после выполнения всех следующих условий.

- Страница была добавлена в страницу свойств с помощью [CPropertySheet:: addPage](../../mfc/reference/cpropertysheet-class.md#addpage).

- Вызвана функция [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [CREATE](../../mfc/reference/cpropertysheet-class.md#create) на странице свойств.

- Пользователь выбрал эту страницу (с вкладками).

Если у вас есть несколько параметров (например, если используется массив), используйте [CPropertySheet:: конструировать](../../mfc/reference/cpropertysheet-class.md#construct) вместо `CPropertyPage`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>CPropertyPage:: Жетпсп

Извлекает структуру [Пропшитпаже](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2) Windows, связанную с объектом `CPropertyPage`.

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на структуру `PROPSHEETPAGE`.

##  <a name="m_psp"></a>CPropertyPage:: m_psp

`m_psp` — это структура, члены которой хранят характеристики [пропшитпаже](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2).

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Remarks

Используйте эту структуру для инициализации внешнего вида страницы свойств после ее конструирования.

Дополнительные сведения об этой структуре, включая список ее членов, см. в разделе `PROPSHEETPAGE` в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>CPropertyPage:: OnApply

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку ОК или применить сейчас.

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если изменения принимаются; в противном случае — 0.

### <a name="remarks"></a>Remarks

Когда платформа вызывает эту функцию, принимаются изменения, внесенные на всех страницах свойств на странице свойств, на странице свойств остается фокус, а `OnApply` возвращает значение TRUE (значение 1). Прежде чем `OnApply` можно будет вызвать с помощью платформы, необходимо вызвать метод [SetModified](#setmodified) и установить для его параметра значение true. Это активирует кнопку Применить сейчас, как только пользователь вносит изменения на странице свойств.

Переопределите эту функцию члена, чтобы указать, какое действие программа принимает, когда пользователь нажмет кнопку "Применить сейчас". При переопределении функция должна возвращать значение TRUE, чтобы принимать изменения, и FALSE, чтобы предотвратить внесение изменений в действие.

Реализация `OnApply` по умолчанию вызывает `OnOK`.

Дополнительные сведения о сообщениях с уведомлениями, отправленных при нажатии пользователем кнопки Применить сейчас или ОК на странице свойств, см. в разделе [PSN_APPLY](/windows/win32/Controls/psn-apply) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CPropertyPage:: ОНОК](#onok).

##  <a name="oncancel"></a>CPropertyPage:: OnCancel

Эта функция-член вызывается платформой при выборе кнопки Отмена.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Remarks

Переопределите эту функцию члена, чтобы выполнить действия кнопки "Отмена". Значение по умолчанию инвертирует все внесенные изменения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>CPropertyPage:: Онкиллактиве

Эта функция-член вызывается платформой, когда страница больше не является активной страницей.

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если данные успешно обновлены; в противном случае — 0.

### <a name="remarks"></a>Remarks

Переопределите эту функцию члена для выполнения специальных задач проверки данных.

Реализация по умолчанию этой функции-члена копирует параметры из элементов управления на странице свойств в переменные-члены страницы свойств. Если данные не были успешно обновлены из-за ошибки проверки данных диалогового окна (DDV), на странице остается фокус.

После успешного возврата этой функции-члена платформа выполнит вызов функции [ОНОК](#onok) страницы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>CPropertyPage:: ОНОК

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку ОК или применить сейчас сразу после того, как платформа вызывает [онкиллактиве](#onkillactive).

```
virtual void OnOK();
```

### <a name="remarks"></a>Remarks

Когда пользователь нажимает кнопку ОК или применить сейчас, платформа получает уведомление [PSN_APPLY](/windows/win32/Controls/psn-apply) на странице свойств. Вызов `OnOK` не будет выполняться при вызове [CPropertySheet::P рессбуттон](../../mfc/reference/cpropertysheet-class.md#pressbutton) , так как страница свойств не отправляет уведомление в этом случае.

Переопределите эту функцию-член, чтобы реализовать дополнительное поведение, относящееся к текущей активной странице, когда пользователь закрывает всю страницу свойств.

Реализация по умолчанию этой функции-члена помечает страницу как "чистую" для отражения того, что данные были обновлены в функции `OnKillActive`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>CPropertyPage:: OnQueryCancel

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Отмена" и перед действием "Отмена".

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение FALSE, чтобы запретить операцию отмены, или значение TRUE, чтобы разрешить ее.

### <a name="remarks"></a>Remarks

Переопределите эту функцию члена, чтобы указать действие, которое программа принимает при нажатии пользователем кнопки "Отмена".

Реализация `OnQueryCancel` по умолчанию возвращает значение TRUE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>CPropertyPage:: OnReset

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Отмена".

```
virtual void OnReset();
```

### <a name="remarks"></a>Remarks

Когда платформа вызывает эту функцию, изменения всех страниц свойств, выполненных ранее нажатием кнопки Apply Now (применить сейчас), отбрасываются, а на странице свойств остается фокус.

Переопределите эту функцию члена, чтобы указать, какое действие программа принимает при нажатии пользователем кнопки "Отмена".

Реализация `OnReset` по умолчанию не выполняет никаких действий.

### <a name="example"></a>Пример

  См. пример для [CPropertyPage:: OnCancel](#oncancel).

##  <a name="onsetactive"></a>CPropertyPage:: Онсетактиве

Эта функция-член вызывается платформой при выборе пользователем страницы и становится активной страницей.

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если страница успешно задана в активном состоянии. в противном случае — 0.

### <a name="remarks"></a>Remarks

Переопределите эту функцию-член для выполнения задач при активации страницы. Переопределение этой функции-члена обычно вызывает версию по умолчанию после обновления элементов данных, позволяя обновлять элементы управления страницы новыми данными.

Реализация по умолчанию создает окно для страницы, если оно не было создано ранее, и делает его активной страницей.

### <a name="example"></a>Пример

  См. пример для [CPropertySheet:: сетфиништекст](../../mfc/reference/cpropertysheet-class.md#setfinishtext).

##  <a name="onwizardback"></a>CPropertyPage:: Онвизардбакк

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "назад" в мастере.

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>Возвращаемое значение

0 для автоматического перехода на следующую страницу; значение-1, чтобы предотвратить изменение страницы. Чтобы перейти к странице, отличной от следующей, возвращается идентификатор отображаемого диалогового окна.

### <a name="remarks"></a>Remarks

Переопределите эту функцию-член, чтобы указать действие, которое должен выполнить пользователь при нажатии кнопки "назад".

Дополнительные сведения о том, как создать страницу свойств типа мастера, см. в разделе [CPropertySheet:: сетвизардмоде](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>CPropertyPage:: Онвизардфиниш

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Готово" в мастере.

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если страница свойств уничтожается по завершении работы мастера. в противном случае — ноль.

### <a name="remarks"></a>Remarks

Когда пользователь нажимает кнопку **Готово** в мастере, платформа вызывает эту функцию. Если `OnWizardFinish` возвращает значение TRUE (ненулевое значение), страница свойств может быть уничтожена (но фактически не уничтожается). Вызовите `DestroyWindow`, чтобы уничтожить страницу свойств. Не вызывайте `DestroyWindow` из `OnWizardFinish`; Это приведет к повреждению кучи или другим ошибкам.

Эту функцию-член можно переопределить, чтобы указать какое-либо действие, которое пользователь должен выполнить при нажатии кнопки Готово. При переопределении этой функции следует возвращать значение FALSE, чтобы предотвратить уничтожение страницы свойств.

Дополнительные сведения о сообщениях с уведомлениями, отправленных при нажатии пользователем кнопки Готово на странице свойств мастера, см. в разделе [PSN_WIZFINISH](/windows/win32/Controls/psn-wizfinish) в Windows SDK.

Дополнительные сведения о том, как создать страницу свойств типа мастера, см. в разделе [CPropertySheet:: сетвизардмоде](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>CPropertyPage:: Онвизарднекст

Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Далее" в мастере.

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>Возвращаемое значение

0 для автоматического перехода на следующую страницу; значение-1, чтобы предотвратить изменение страницы. Чтобы перейти к странице, отличной от следующей, возвращается идентификатор отображаемого диалогового окна.

### <a name="remarks"></a>Remarks

Переопределите эту функцию-член, чтобы указать какое-либо действие, которое пользователь должен выполнить при нажатии кнопки "Далее".

Дополнительные сведения о том, как создать страницу свойств типа мастера, см. в разделе [CPropertySheet:: сетвизардмоде](../../mfc/reference/cpropertysheet-class.md#setwizardmode).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>CPropertyPage:: Куерисиблингс

Вызовите эту функцию-член, чтобы перенаправить сообщение на каждую страницу в странице свойств.

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
Указывает дополнительные сведения, зависящие от сообщений.

*lParam*<br/>
Указывает дополнительные сведения, зависящие от сообщений

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение со страницы на странице свойств или 0, если все страницы возвращают значение 0.

### <a name="remarks"></a>Remarks

Если страница возвращает ненулевое значение, вкладка свойств не отправляет сообщение на последующие страницы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>CPropertyPage:: SetModified

Вызовите эту функцию-член, чтобы включить или отключить кнопку "Применить сейчас" в зависимости от того, должны ли параметры на странице свойств применяться к соответствующему внешнему объекту.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Параметры

*бчанжед*<br/>
Значение TRUE указывает, что параметры страницы свойств были изменены с момента последнего применения. Значение FALSE указывает, что параметры страницы свойств применены или должны игнорироваться.

### <a name="remarks"></a>Remarks

Платформа отслеживает, какие страницы являются «грязными», то есть страницы свойств, для которых вызвана `SetModified( TRUE )`. Кнопка Применить сейчас всегда будет включена при вызове `SetModified( TRUE )` для одной из страниц. Кнопка применить Now будет отключена при вызове `SetModified( FALSE )` для одной из страниц, но только в случае, если ни одна из других страниц не является "грязной".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример CMNCTRL1 для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример CMNCTRL2 для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример ПРОПДЛГ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPropertySheet](../../mfc/reference/cpropertysheet-class.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
