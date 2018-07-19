---
title: Класс CPropertyPage | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6a5b0e031aebb658b4da20d3aa9a6dd47f8c2a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851565"
---
# <a name="cpropertypage-class"></a>Cpropertypage-класс
Представляет отдельные страницы вкладки свойств, также известные как диалоговое окно вкладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|Создает объект `CPropertyPage`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|Изменяет "ОК" для чтения Close и отключает кнопки "Отмена", при изменении неустранимой модальную страницу свойств на странице.|  
|[CPropertyPage::Construct](#construct)|Создает объект `CPropertyPage`. Используйте `Construct` , если вы хотите указать параметры во время выполнения или при использовании массивов.|  
|[CPropertyPage::GetPSP](#getpsp)|Извлекает Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структуры, связанные с `CPropertyPage` объекта.|  
|[CPropertyPage::OnApply](#onapply)|Вызывается платформой при нажатии кнопка "Применить".|  
|[CPropertyPage::OnCancel](#oncancel)|Вызывается платформой при нажатии кнопки "Отмена".|  
|[CPropertyPage::OnKillActive](#onkillactive)|Вызывается платформой, если текущая страница больше не является активной страницей. Выполните проверку данных.|  
|[CPropertyPage::OnOK](#onok)|Вызывается платформой при нажатии ОК, теперь применяются то есть кнопка "Закрыть".|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Вызывается платформой при нажатии кнопки "Отмена", а также перед отмены.|  
|[CPropertyPage::OnReset](#onreset)|Вызывается платформой при нажатии кнопки "Отмена".|  
|[CPropertyPage::OnSetActive](#onsetactive)|Вызывается платформой, когда страница становится активной страницей.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Вызывается платформой при нажатии кнопки "Назад" при использовании листа свойств мастера.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Вызывается платформой при нажатии кнопки "Готово" при использовании листа свойств мастера.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Вызывается платформой при нажатии кнопки "Далее" при использовании листа свойств мастера.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|Перенаправляет сообщение на каждую страницу свойств.|  
|[CPropertyPage::SetModified](#setmodified)|Вызов, активация и деактивация кнопка "Применить".|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структуры. Предоставляет доступ к параметрам страницу основных свойств.|  
  
## <a name="remarks"></a>Примечания  
 Как с помощью стандартных диалоговых, наследуйте класс от `CPropertyPage` для каждой страницы в таблице свойств. Чтобы использовать `CPropertyPage`-производных объектов, сначала создайте [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) объекта, а затем создать объект для каждой страницы, который находится в окне свойств. Вызовите [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) для каждой страницы на листе и затем откройте окно свойств путем вызова [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) для модальную страницу свойств, или [CPropertySheet:: Создание](../../mfc/reference/cpropertysheet-class.md#create) для немодальный лист свойств.  
  
 Можно создать тип вкладки диалогового окна вызывается мастер, который состоит из свойств последовательностью страницы свойств, которые проводят пользователя через шаги операции, такие как Настройка устройства или создание информационного бюллетеня. В диалоговом окне вкладку тип мастера на страницах свойств не имеют вкладки и только одно свойство страница видна за раз. Кроме того вместо кнопки "ОК" и "Apply Now, диалоговое окно мастера вкладки имеет кнопку" Назад ", кнопки следующего или" Готово "и" Отмена ".  
  
 Дополнительные сведения о настройке свойств в качестве мастера, см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Дополнительные сведения об использовании `CPropertyPage` объектов, см. в статье [вкладки свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose  
 Вызывайте эту функцию после неустранимой изменения данных на странице модальную страницу свойств.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция изменяет "ОК" для закрытия и отключение кнопки "Отмена". Это изменение оповещений, которые пользователь, что изменение не постоянной, а изменения не может быть отменено.  
  
 `CancelToClose` Функция-член ничего не делает в немодальный лист свойств, так как немодальный лист свойств не имеют кнопки "Отмена", по умолчанию.  
  
### <a name="example"></a>Пример  
  См. в примере [CPropertyPage::QuerySiblings](#querysiblings).  
  
##  <a name="construct"></a>  CPropertyPage::Construct  
 Эта функция-член для создания вызова `CPropertyPage` объекта.  
  
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
 *nIDTemplate*  
 Идентификатор шаблона, который использовался для этой страницы.  
  
 *nIDCaption*  
 Идентификатор имени должно быть помещено в вкладке этой страницы. Если значение равно 0, имя будет браться из шаблона диалогового окна для этой страницы.  
  
 *lpszTemplateName*  
 Содержащий заканчивающуюся нулем строку, имя ресурса шаблона.  
  
 *nIDHeaderTitle*  
 Идентификатор имени должно быть помещено в расположение заголовка заголовка страницы свойств. По умолчанию 0.  
  
 *nIDHeaderSubTitle*  
 Идентификатор имени должно быть помещено в расположение подзаголовок заголовка страницы свойств. По умолчанию 0.  
  
### <a name="remarks"></a>Примечания  
 Объект отображается после соблюдении всех следующих условий:  
  
-   Страницы был добавлен в лист свойств с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Окно свойств [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [создать](../../mfc/reference/cpropertysheet-class.md#create) функция была вызвана.  
  
-   Пользователь выбрал (перейти к объекту) этой странице.  
  
 Вызовите `Construct` Если один из конструкторов класса не вызывается. `Construct` Функция-член является гибким, поскольку можно не указывайте параметр инструкции и затем указать несколько параметров и конструкции в любой момент в коде.  
  
 Необходимо использовать `Construct` при работе с массивами, и необходимо вызвать `Construct` для каждого элемента массива, чтобы члены данных присваиваются соответствующие значения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage  
 Создает объект `CPropertyPage`.  
  
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
 *nIDTemplate*  
 Идентификатор шаблона, который использовался для этой страницы.  
  
 *nIDCaption*  
 Идентификатор имени должно быть помещено в вкладке этой страницы. Если значение равно 0, имя будет браться из шаблона диалогового окна для этой страницы.  
  
 *dwSize*  
 *lpszTemplateName*  
 Указывает строку, содержащую имя шаблона для этой страницы. Не может принимать значение NULL.  
  
 *nIDHeaderTitle*  
 Идентификатор имени должно быть помещено в расположение заголовка заголовка страницы свойств.  
  
 *nIDHeaderSubTitle*  
 Идентификатор имени должно быть помещено в расположение подзаголовок заголовка страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Объект отображается после соблюдении всех следующих условий:  
  
-   Страницы был добавлен в лист свойств с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Окно свойств [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [создать](../../mfc/reference/cpropertysheet-class.md#create) функция была вызвана.  
  
-   Пользователь выбрал (перейти к объекту) этой странице.  
  
 Если у вас есть несколько параметров (например, если вы используете массив), используйте [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) вместо `CPropertyPage`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>  CPropertyPage::GetPSP  
 Извлекает Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структуры, связанные с `CPropertyPage` объекта.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `PROPSHEETPAGE` структуры.  
  
##  <a name="m_psp"></a>  CPropertyPage::m_psp  
 `m_psp` — это структура, члены которой хранения характеристики [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта структура используется для инициализации внешний вид страницы свойств после его создания.  
  
 Дополнительные сведения об этой структуре, включая список его элементов, см. в разделе `PROPSHEETPAGE` в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>  CPropertyPage::OnApply  
 Эта функция-член вызывается платформой, когда пользователь выбирает ОК "или" Кнопка "Применить".  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменения принимаются; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Когда платформа вызывает эту функцию, принимаются изменения, внесенные на всех страницах свойств в окне свойств, свойств сохраняет фокус, и `OnApply` возвращает значение TRUE (значение 1). Прежде чем `OnApply` может вызываться платформой, вам необходимо вызвать метод [SetModified](#setmodified) и задайте для его параметра значение true. Это активирует кнопка "Применить", как только пользователь вносит изменения на странице свойств.  
  
 Переопределите эта функция-член для указания программа принимает при нажатии кнопка "Применить". При переопределении метода, данная функция должна возвращать значение TRUE, чтобы принять изменения и значение FALSE, чтобы предотвратить изменения вступают в силу.  
  
 Реализация по умолчанию `OnApply` вызовы `OnOK`.  
  
 Дополнительные сведения о сообщениях уведомлений, отправленных при нажатии применить сейчас или кнопку "ОК" на странице свойств см. в разделе [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
  См. в примере [CPropertyPage::OnOK](#onok).  
  
##  <a name="oncancel"></a>  CPropertyPage::OnCancel  
 Эта функция-член вызывается платформой при нажатии кнопки "Отмена".  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите эта функция-член для выполнения действий кнопку "Отмена". Значение по умолчанию отменяет все изменения, которые были внесены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive  
 Эта функция-член вызывается платформой, когда страница перестает быть активной страницей.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные были обновлены успешно, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эта функция-член для выполнения задач проверки специальных данных.  
  
 Реализация по умолчанию эта функция-член копирует параметры из элементов управления на странице свойств переменных-членов страницы свойств. Если данные не были успешно обновлены из-за ошибки проверки (DDV) данных диалогового окна, страницы сохраняет фокус.  
  
 После успешного возврата эта функция-член платформа вызывает страницы [OnOK](#onok) функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>  CPropertyPage::OnOK  
 Эта функция-член вызывается платформой, когда пользователь выбирает ОК или кнопка "Применить", сразу после платформа вызывает [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает ОК или кнопка "Применить", платформа получает [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) уведомлений на странице свойств. Вызов `OnOK` не будет выполняться при вызове метода [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) так, как на страницу свойств в этом случае не отправлять уведомления.  
  
 Переопределите эту функцию-член для реализации дополнительное поведение, характерное для текущей активной страницы, когда пользователь закрывает окно всей свойств.  
  
 Реализация по умолчанию эта функция-член помечает страницу как «очистить», чтобы отразить, что данные были обновлены в `OnKillActive` функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel  
 Эта функция-член вызывается платформой при нажатии кнопки "Отмена" и до отмены было выполнено действие.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение FALSE, чтобы предотвратить операции отмены или значение TRUE, чтобы разрешить его.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию члена, чтобы указать действие, которое программа принимает при нажатии кнопки "Отмена".  
  
 Реализация по умолчанию `OnQueryCancel` возвращает значение TRUE.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>  CPropertyPage::OnReset  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопки "Отмена".  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Примечания  
 Когда платформа вызывает эту функцию, изменения ко всем страницам свойств, внесенные пользователем, ранее нажмите кнопку "Применить", будут отменены, и окно свойств сохраняет фокус.  
  
 Переопределите эта функция-член для указания программа принимает при нажатии кнопки "Отмена".  
  
 Реализация по умолчанию `OnReset` не выполняет никаких действий.  
  
### <a name="example"></a>Пример  
  См. в примере [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive  
 Эта функция-член вызывается платформой при страницы, выбранный пользователем и становится активной страницей.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если страницы был успешно задан активно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределение для выполнения задач, когда страница активируется эта функция-член. Переопределенный эта функция-член обычно вызывается версия по умолчанию после обновления элементов данных, чтобы его можно обновить элементы управления страницы новыми данными.  
  
 Реализация по умолчанию создает окно для страницы, если не создали и делает активной страницей.  
  
### <a name="example"></a>Пример  
  См. в примере [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack  
 Эта функция-член вызывается платформой, когда пользователь щелкает "Назад" в мастере.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, чтобы автоматически перейти на следующую страницу; значение -1, чтобы предотвратить изменение страницы. Чтобы перейти на страницу, отличном от того, далее, возвращают идентификатор диалогового окна для отображения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эта функция-член для указания некоторых операций, которые должен выполнить пользователь при нажатии кнопки «Назад».  
  
 Дополнительные сведения о том, как сделать листа свойств мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Готово", с помощью мастера.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств уничтожается после завершения работы мастера; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает **Готово** кнопку в мастере, платформа вызывает эту функцию; когда `OnWizardFinish` возвращает значение TRUE (ненулевое значение), окно свойств может уничтожить (но не удаляется). Вызовите `DestroyWindow` уничтожить окно свойств. Не вызывайте `DestroyWindow` из `OnWizardFinish`; это вызовет повреждение кучи или другие ошибки.  
  
 Эта функция-член для указания некоторые действия, которые должен выполнить пользователь при нажатии кнопки «Готово», можно переопределить. При переопределении этой функции, возвращать значение FALSE, чтобы предотвратить свойств от уничтожения.  
  
 Дополнительные сведения о сообщениях уведомлений, отправленных при нажатии кнопки «Готово» в окне свойств мастера см. в разделе [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) в пакете Windows SDK.  
  
 Дополнительные сведения о том, как сделать листа свойств мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Далее" в мастере.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, чтобы автоматически перейти на следующую страницу; значение -1, чтобы предотвратить изменение страницы. Чтобы перейти на страницу, отличном от того, далее, возвращают идентификатор диалогового окна для отображения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эта функция-член для указания некоторых операций, которые должен выполнить пользователь при нажатии "Далее".  
  
 Дополнительные сведения о том, как сделать листа свойств мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings  
 Вызовите эту функцию-член для пересылки сообщения для каждой страницы в окне свойств.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 *wParam*  
 Указывает Дополнительные сведения, зависящие от сообщения.  
  
 *lParam*  
 Указывает Дополнительные сведения, зависящие от сообщения  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение со страницы в окне свойств, или 0, если все страницы возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Если страница возвращает ненулевое значение, окно свойств не отправляет сообщение на последующих страницах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>  CPropertyPage::SetModified  
 Вызовите эту функцию-член для включения или отключения кнопка "Применить", зависимости от того, следует ли применять параметры на странице свойств в соответствующий внешний объект.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bChanged*  
 Значение TRUE указывает, что параметрах страницы свойств были изменены с момента последнего они были применены; Значение FALSE, чтобы указать, что были применены параметры страницы, или следует игнорировать.  
  
### <a name="remarks"></a>Примечания  
 Framework хранит записи, из которых страницы являются «грязный», то есть, страницы свойств, для которых вы вызвали `SetModified( TRUE )`. Всегда будет включена кнопка "Применить", если вы вызываете `SetModified( TRUE )` для одной из страниц. Кнопка "Применить" будет отключена при вызове `SetModified( FALSE )` для одной из страниц, но только если ни один из других страниц «грязный».  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Пример MFC: SNAPVW](../../visual-cpp-samples.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Cpropertysheet-класс](../../mfc/reference/cpropertysheet-class.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)
