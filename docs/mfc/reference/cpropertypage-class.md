---
title: "CPropertyPage-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- property pages, CPropertyPage class
- dialog boxes, tabs
- CPropertyPage class
- tab dialog boxes
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 13fb9befb6d1549493afa6cbed53ec4d41443c3a
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertypage-class"></a>CPropertyPage-класс
Представляет отдельные страницы вкладки свойств, также известные как диалоговое окно вкладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|Создает объект `CPropertyPage`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|Изменяет кнопку ОК, чтобы закрыть чтения и отключает кнопку "Отмена", после неустранимой изменения на странице модальную страницу свойств.|  
|[CPropertyPage::Construct](#construct)|Создает объект `CPropertyPage`. Используйте `Construct` , если необходимо указывать параметры во время выполнения или при использовании массивов.|  
|[CPropertyPage::GetPSP](#getpsp)|Извлекает Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структура, связанная с `CPropertyPage` объекта.|  
|[CPropertyPage::OnApply](#onapply)|Вызывается платформой, при нажатии кнопки Применить.|  
|[CPropertyPage::OnCancel](#oncancel)|Вызывается платформой, при нажатии кнопки "Отмена".|  
|[CPropertyPage::OnKillActive](#onkillactive)|Вызывается платформой, если текущая страница больше не является активной страницы. Выполните проверку данных.|  
|[CPropertyPage::OnOK](#onok)|Вызывается инфраструктурой при щелчке ОК, применить сейчас или кнопку Закрыть.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Вызывается инфраструктурой при нажатии кнопки "Отмена" и до отмены.|  
|[CPropertyPage::OnReset](#onreset)|Вызывается платформой, при нажатии кнопки "Отмена".|  
|[CPropertyPage::OnSetActive](#onsetactive)|Вызывается платформой, когда страница становится активной страницы.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Вызывается платформой, при нажатии кнопки «Назад» при использовании листа свойств мастера.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Вызывается платформой, при нажатии кнопки "Готово" при использовании листа свойств мастера.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Вызывается платформой, при нажатии кнопки Далее при использовании листа свойств мастера.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|Пересылает сообщение на каждую страницу свойств.|  
|[CPropertyPage::SetModified](#setmodified)|Вызов включить или отключить кнопку Применить.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структуры. Предоставляет доступ к параметрам страницу основных свойств.|  
  
## <a name="remarks"></a>Примечания  
 Как со стандартным диалоговым окнам, наследуйте класс от `CPropertyPage` для каждой страницы в таблице свойств. Для использования `CPropertyPage`-производных объектов, сначала создайте [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) объекта, а затем создать объект для каждой страницы, который находится в окне свойств. Вызов [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) для каждой страницы в таблице и затем откройте окно свойств путем вызова [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) для модальных свойств или [CPropertySheet::Create](../../mfc/reference/cpropertysheet-class.md#create) для страницы вкладки свойств.  
  
 Можно создать тип вкладка диалогового окна вызывается мастер, который состоит из свойств последовательностью страницы свойств, которые проводят пользователя через последовательность шагов операции, такие как настройки устройства или создание информационного бюллетеня. В диалоговом окне вкладку тип мастера страницы свойств нет вкладки и только одно свойство страница видна одновременно. Кроме того вместо кнопки OK и Apply Now, диалоговое окно вкладки тип мастера имеет кнопки Back, далее или Готово, кнопки и кнопки «Отмена».  
  
 Дополнительные сведения о настройке свойств в качестве мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Дополнительные сведения об использовании `CPropertyPage` объектов, см. в статье [вкладки свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="a-namecanceltoclosea--cpropertypagecanceltoclose"></a><a name="canceltoclose"></a>CPropertyPage::CancelToClose  
 Эта функция вызывается после неустранимой изменений данных на странице модальную страницу свойств.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция изменяет кнопку OK для закрытия и отключение кнопки "Отмена". Это изменение оповещения, что изменение является постоянным и изменения пользователя не может быть отменено.  
  
 `CancelToClose` Функция-член не выполняет никаких действий в немодальное свойств, поскольку немодальный лист свойств не имеет кнопки «Отмена» по умолчанию.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertyPage::QuerySiblings](#querysiblings).  
  
##  <a name="a-nameconstructa--cpropertypageconstruct"></a><a name="construct"></a>CPropertyPage::Construct  
 Вызов этой функции-члена для создания `CPropertyPage` объекта.  
  
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
 `nIDTemplate`  
 Идентификатор шаблона, используемый для этой страницы.  
  
 `nIDCaption`  
 Идентификатор имени помещается на вкладке для этой страницы. Если значение равно 0, имя будет взято из шаблона диалогового окна для этой страницы.  
  
 `lpszTemplateName`  
 Содержит нулем строку, имя ресурса шаблона.  
  
 `nIDHeaderTitle`  
 Идентификатор имени должно быть помещено в положение заголовка заголовка страницы свойств. По умолчанию 0.  
  
 `nIDHeaderSubTitle`  
 Идентификатор имени должно быть помещено в расположение подзаголовок верхний колонтитул страницы свойств. По умолчанию 0.  
  
### <a name="remarks"></a>Примечания  
 Объект отображается после выполняются все следующие условия:  
  
-   Страница будет добавлен свойства стилей с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Окно свойств [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [создать](../../mfc/reference/cpropertysheet-class.md#create) функция была вызвана.  
  
-   Пользователь выбрал (перейти к) на этой странице.  
  
 Вызов **создания** Если один из конструкторов класса не вызывается. `Construct` Функция-член является гибким, поскольку вы не указывайте параметр инструкции и затем указать несколько параметров и построение в любой точке в коде.  
  
 Необходимо использовать `Construct` при работе с массивами, и необходимо вызвать **создания** для каждого элемента массива, чтобы члены данных назначаются необходимые значения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#112;](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="a-namecpropertypagea--cpropertypagecpropertypage"></a><a name="cpropertypage"></a>CPropertyPage::CPropertyPage  
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
 `nIDTemplate`  
 Идентификатор шаблона, используемый для этой страницы.  
  
 `nIDCaption`  
 Идентификатор имени помещается на вкладке для этой страницы. Если значение равно 0, имя будет взято из шаблона диалогового окна для этой страницы.  
  
 `dwSize`  
 `lpszTemplateName`  
 Указывает строку, содержащую имя шаблона для этой страницы. Не может быть **NULL**.  
  
 `nIDHeaderTitle`  
 Идентификатор имени должно быть помещено в положение заголовка заголовка страницы свойств.  
  
 `nIDHeaderSubTitle`  
 Идентификатор имени должно быть помещено в расположение подзаголовок верхний колонтитул страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Объект отображается после выполняются все следующие условия:  
  
-   Страница будет добавлен свойства стилей с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Окно свойств [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [создать](../../mfc/reference/cpropertysheet-class.md#create) функция была вызвана.  
  
-   Пользователь выбрал (перейти к) на этой странице.  
  
 Если у вас есть несколько параметров (например, если вы используете массив), используйте [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) вместо `CPropertyPage`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#113;](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="a-namegetpspa--cpropertypagegetpsp"></a><a name="getpsp"></a>CPropertyPage::GetPSP  
 Извлекает Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структура, связанная с `CPropertyPage` объекта.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на **PROPSHEETPAGE** структуры.  
  
##  <a name="a-namempspa--cpropertypagempsp"></a><a name="m_psp"></a>CPropertyPage::m_psp  
 `m_psp`представляет собой структуру, члены которого хранения характеристики [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте эту структуру для инициализации внешний вид страницы свойств после его создания.  
  
 Дополнительные сведения об этой структуры, включая список ее членов в разделе **PROPSHEETPAGE** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#128;](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="a-nameonapplya--cpropertypageonapply"></a><a name="onapply"></a>CPropertyPage::OnApply  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку OK, или кнопку Применить.  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эти изменения принимаются; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Когда платформа вызывает эту функцию, принимаются изменения, внесенные на всех страницах свойств в окне свойств, окно свойств сохраняет фокус, и `OnApply` возвращает **TRUE** (значение 1). Перед `OnApply` может быть вызван платформой, то необходимо вызвать метод [SetModified](#setmodified) и задайте параметра **TRUE**. Это активирует кнопку Применить сразу же после внесения изменений на странице свойств.  
  
 Переопределите эту функцию-член для указания принимает программы, когда пользователь нажимает кнопку Применить. При переопределении метода, функция должна возвращать **TRUE** для принятия изменений и **FALSE** для предотвращения изменения вступают в силу.  
  
 Реализация по умолчанию `OnApply` вызовов `OnOK`.  
  
 Дополнительные сведения о сообщениях уведомлений, отправленных при нажатии применить сейчас или кнопку OK в окне свойств в разделе [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertyPage::OnOK](#onok).  
  
##  <a name="a-nameoncancela--cpropertypageoncancel"></a><a name="oncancel"></a>CPropertyPage::OnCancel  
 Эта функция-член вызывается инфраструктурой при выборе кнопки "Отмена".  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения действий кнопку "Отмена". Значение по умолчанию отменяет все изменения, которые были внесены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#114;](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="a-nameonkillactivea--cpropertypageonkillactive"></a><a name="onkillactive"></a>CPropertyPage::OnKillActive  
 Эта функция-член вызывается платформой, если страница больше не является активной страницы.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные были обновлены успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач проверки специальных данных.  
  
 Реализация по умолчанию эта функция-член копирует параметры из элементов управления на странице свойств к переменным-членам страницы свойств. Если данные не были успешно обновлены из-за ошибки при проверке (DDV) данных диалогового окна, страницы сохраняет фокус.  
  
 После успешного возвращает эта функция-член, платформа вызывает страницы [OnOK](#onok) функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#115;](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="a-nameonoka--cpropertypageonok"></a><a name="onok"></a>CPropertyPage::OnOK  
 Эта функция-член вызывается платформой, когда пользователь выбирает ОК или кнопку Применить, сразу после платформа вызывает функцию [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает ОК или кнопка Apply Now, платформа получает [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) уведомления на странице свойств. Вызов `OnOK` не будет выполняться при вызове [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) , так как на странице свойств в этом случае не отправлять уведомления.  
  
 Переопределение для реализации дополнительное поведение, характерное для текущей активной страницы, когда пользователь закрывает окно свойств всего эта функция-член.  
  
 Реализация по умолчанию эта функция-член помечает страницу как «очистить» для отражения того, что данные были обновлены в `OnKillActive` функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&116;](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="a-nameonquerycancela--cpropertypageonquerycancel"></a><a name="onquerycancel"></a>CPropertyPage::OnQueryCancel  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Отмена" и до отмены было выполнено действие.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **FALSE** для предотвращения операции отмены или значение TRUE, чтобы разрешить его.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для задания действия, которую программа принимает, когда пользователь нажимает кнопку "Отмена".  
  
 Реализация по умолчанию `OnQueryCancel` возвращает **TRUE**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#117;](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="a-nameonreseta--cpropertypageonreset"></a><a name="onreset"></a>CPropertyPage::OnReset  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Отмена".  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Примечания  
 Когда платформа вызывает эту функцию, изменения все страницы свойств, внесенные пользователем, ранее кнопки "Применить", удаляются, и окно свойств сохраняет фокус.  
  
 Переопределите эту функцию-член для указания программа принимает, когда пользователь нажимает кнопку "Отмена".  
  
 Реализация по умолчанию `OnReset` не выполняет никаких действий.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="a-nameonsetactivea--cpropertypageonsetactive"></a><a name="onsetactive"></a>CPropertyPage::OnSetActive  
 Эта функция-член вызывается инфраструктурой при выбранной пользователем страницы и становится активной страницей.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если страницы был успешно установлен активно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач, когда страница активируется. Переопределение метода эта функция-член версию по умолчанию обычно вызывается после обновления элементов данных, чтобы пользователи могли обновлять элементы управления страницы новыми данными.  
  
 Реализация по умолчанию создает окно страницы, если не созданного ранее, а затем делает активной страницы.  
  
### <a name="example"></a>Пример  
  В примере показано [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="a-nameonwizardbacka--cpropertypageonwizardback"></a><a name="onwizardback"></a>CPropertyPage::OnWizardBack  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку Назад в мастер.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, чтобы автоматически перейти на следующую страницу; значение -1, чтобы предотвратить изменение страницы. Для перехода на страницу, не является следующим возвращают идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для указания некоторое действие, которое должен выполнить пользователь при нажатии кнопки «Назад».  
  
 Дополнительные сведения о настройке свойств тип мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#118;](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="a-nameonwizardfinisha--cpropertypageonwizardfinish"></a><a name="onwizardfinish"></a>CPropertyPage::OnWizardFinish  
 Эта функция-член вызывается платформой, когда пользователь нажимает на кнопку Готово в мастере.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств уничтожается после завершения работы мастера; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает **Готово** кнопку в мастере, платформа вызывает эту функцию; когда `OnWizardFinish` возвращает **TRUE** (ненулевое значение), окно свойств может быть уничтожен (но не удаляется). Вызов `DestroyWindow` уничтожить окно свойств. Не следует вызывать `DestroyWindow` из `OnWizardFinish`; это будет вызвать повреждение кучи или другие ошибки.  
  
 Можно переопределить эту функцию-член для указания некоторое действие, которое должен выполнить пользователь при нажатии кнопки "Готово". При переопределении данной функции, возвращать **FALSE** для предотвращения удаления страницы свойств.  
  
 Дополнительные сведения о сообщениях уведомлений, отправленных при нажатии кнопки «Готово» в окне свойств мастера см. в разделе [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о настройке свойств тип мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#119;](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#120;](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#121;](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#122;](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="a-nameonwizardnexta--cpropertypageonwizardnext"></a><a name="onwizardnext"></a>CPropertyPage::OnWizardNext  
 Эта функция-член вызывается платформой, когда пользователь нажимает на кнопку "Далее" в мастере.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, чтобы автоматически перейти на следующую страницу; значение -1, чтобы предотвратить изменение страницы. Для перехода на страницу, не является следующим возвращают идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для указания некоторое действие, которое должен выполнить пользователь, когда нажимается кнопка «Далее».  
  
 Дополнительные сведения о настройке свойств тип мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#123;](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="a-namequerysiblingsa--cpropertypagequerysiblings"></a><a name="querysiblings"></a>CPropertyPage::QuerySiblings  
 Вызовите эту функцию-член для пересылки сообщения на каждую страницу в окне свойств.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `wParam`  
 Задает дополнительные сведения, зависящие от сообщения.  
  
 `lParam`  
 Указывает Дополнительные сведения, зависящие от сообщения  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение из страницы в окне свойств, или 0, если все страницы возвращают значение 0.  
  
### <a name="remarks"></a>Примечания  
 Если страница возвращает ненулевое значение, окно свойств не отправляет сообщение последующих страниц.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#124;](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#125;](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#126;](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="a-namesetmodifieda--cpropertypagesetmodified"></a><a name="setmodified"></a>CPropertyPage::SetModified  
 Вызовите эту функцию-член для включения или отключения кнопка Apply Now, зависимости от того, следует ли применять параметры на странице свойств для соответствующего внешнего объекта.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bChanged`  
 **Значение TRUE,** для указания, что параметры страницы свойств были изменены со времени последнего, они были применены; **FALSE** были применены параметры страницы свойств или игнорироваться.  
  
### <a name="remarks"></a>Примечания  
 Платформа поддерживает отслеживание, из которых страницы «грязных», то есть, страницы свойств, для которых был вызван **SetModified (TRUE)**. Кнопка Apply Now будет всегда включен, при вызове **SetModified (TRUE)** для одной из страниц. Кнопка Apply Now будет отключена при вызове **SetModified (FALSE)** для одной из страниц, но только если ни один из других страниц «грязным».  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#127;](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Пример MFC SNAPVW](../../visual-cpp-samples.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPropertySheet-класс](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

