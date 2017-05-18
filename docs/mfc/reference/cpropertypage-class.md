---
title: "CPropertyPage-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: f14dfe29a6fa941192c2cfe792f16e4b032af941
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

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
|[CPropertyPage::CancelToClose](#canceltoclose)|Изменяет кнопку ОК, чтобы закрыть чтения и отключает кнопку "Отмена", при изменении текста без возможности восстановления на странице модальную страницу свойств.|  
|[CPropertyPage::Construct](#construct)|Создает объект `CPropertyPage`. Используйте `Construct` , если вы хотите указать параметры во время выполнения или при использовании массивов.|  
|[CPropertyPage::GetPSP](#getpsp)|Извлекает Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структур, связанных с `CPropertyPage` объекта.|  
|[CPropertyPage::OnApply](#onapply)|Вызывается платформой, когда нажата кнопка "Применить".|  
|[CPropertyPage::OnCancel](#oncancel)|Вызывается платформой при нажатии кнопки "Отмена".|  
|[CPropertyPage::OnKillActive](#onkillactive)|Вызывается платформой, если текущая страница больше не является активной странице. Выполните проверку данных.|  
|[CPropertyPage::OnOK](#onok)|Вызывается платформой при щелчке ОК, применить сейчас или кнопку Закрыть.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Вызывается платформой при нажатии кнопки "Отмена", а также перед отмены.|  
|[CPropertyPage::OnReset](#onreset)|Вызывается платформой при нажатии кнопки "Отмена".|  
|[CPropertyPage::OnSetActive](#onsetactive)|Вызывается платформой, когда страница становится активной странице.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Вызывается платформой при нажатии кнопки «Назад» при использовании листа свойств мастера.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Вызывается платформой при нажатии кнопки "Готово" при использовании листа свойств мастера.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Вызывается платформой при нажатии кнопки "Далее" при использовании листа свойств мастера.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|Пересылает сообщение на каждую страницу свойств.|  
|[CPropertyPage::SetModified](#setmodified)|Вызов активировать или деактивировать кнопка "Применить".|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структуры. Предоставляет доступ к параметрам страницу основных свойств.|  
  
## <a name="remarks"></a>Примечания  
 Как со стандартным диалоговым окнам, наследуйте класс от `CPropertyPage` для каждой страницы в таблице свойств. Для использования `CPropertyPage`-производных объектов, сначала создайте [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) объекта, а затем создать объект для каждой страницы, входящий в окне свойств. Вызовите [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) для каждой страницы в таблице и затем откройте окно свойств путем вызова [CPropertySheet::DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) для модальную страницу свойств, или [CPropertySheet::Create](../../mfc/reference/cpropertysheet-class.md#create) для немодальный лист свойств.  
  
 Можно создать тип вкладка диалогового окна вызван мастер, который состоит из окна свойств последовательностью страницы свойств, которые проводят пользователя через шаги операции, такие как Настройка устройства или создание информационный бюллетень. В диалоговом окне вкладку тип мастера страницы свойств не имеют вкладок и только одно свойство страница видна одновременно. Кроме того вместо кнопки OK и применить, диалоговое окно вкладки тип мастера имеет кнопка "Назад", далее или Готово кнопки и кнопки "Отмена".  
  
 Дополнительные сведения о настройке свойств в качестве мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Дополнительные сведения об использовании `CPropertyPage` объектов, см. в статье [вкладки свойств и страницы свойств](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>CPropertyPage::CancelToClose  
 Эта функция вызывается после неустранимой изменений данных на странице модальную страницу свойств.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция изменяет кнопки «ОК» для закрытия и отключает кнопку "Отмена". Это изменение оповещения пользователя, что изменение является постоянной, а изменения не может быть отменено.  
  
 `CancelToClose` Функция-член не выполняет никаких действий, в немодальный лист свойств, так как немодальный лист свойств не имеет кнопку «Отмена» по умолчанию.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertyPage::QuerySiblings](#querysiblings).  
  
##  <a name="construct"></a>CPropertyPage::Construct  
 Вызовите эту функцию-член для создания `CPropertyPage` объекта.  
  
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
 Идентификатор имени должен располагаться на вкладке этой страницы. Если значение равно 0, имя будет взято из шаблона диалогового окна для этой страницы.  
  
 `lpszTemplateName`  
 Содержит строку символом null, имя ресурса шаблона.  
  
 `nIDHeaderTitle`  
 Идентификатор имени должно быть помещено в расположение заголовка заголовка страницы свойств. По умолчанию 0.  
  
 `nIDHeaderSubTitle`  
 Идентификатор имени должно быть помещено в расположение подзаголовок заголовка страницы свойств. По умолчанию 0.  
  
### <a name="remarks"></a>Примечания  
 Объект отображается после соблюдении всех следующих условий:  
  
-   Страница добавлена в лист свойств с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Окно свойств [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [создать](../../mfc/reference/cpropertysheet-class.md#create) функция была вызвана.  
  
-   Пользователь выбрал (с вкладками для) этой страницы.  
  
 Вызовите **создания** Если один из конструкторов класса не вызывается. `Construct` Функция-член является гибким, поскольку вы не указывайте параметр инструкции и затем указать несколько параметров и конструкции в любом месте в коде.  
  
 Необходимо использовать `Construct` при работе с массивами и необходимо вызвать **создания** для каждого элемента массива, чтобы члены данных назначаются соответствующих значений.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>CPropertyPage::CPropertyPage  
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
 Идентификатор имени должен располагаться на вкладке этой страницы. Если значение равно 0, имя будет взято из шаблона диалогового окна для этой страницы.  
  
 `dwSize`  
 `lpszTemplateName`  
 Указывает строку, содержащую имя шаблона для этой страницы. Не может быть **NULL**.  
  
 `nIDHeaderTitle`  
 Идентификатор имени должно быть помещено в расположение заголовка заголовка страницы свойств.  
  
 `nIDHeaderSubTitle`  
 Идентификатор имени должно быть помещено в расположение подзаголовок заголовка страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Объект отображается после соблюдении всех следующих условий:  
  
-   Страница добавлена в лист свойств с помощью [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Окно свойств [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) или [создать](../../mfc/reference/cpropertysheet-class.md#create) функция была вызвана.  
  
-   Пользователь выбрал (с вкладками для) этой страницы.  
  
 Если имеется несколько параметров (например, если вы используете массив), используйте [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) вместо `CPropertyPage`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>CPropertyPage::GetPSP  
 Извлекает Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) структур, связанных с `CPropertyPage` объекта.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на **PROPSHEETPAGE** структуры.  
  
##  <a name="m_psp"></a>CPropertyPage::m_psp  
 `m_psp`— это структура, члены которой хранения характеристики [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте эту структуру для инициализации внешний вид страницы свойств, после его создания.  
  
 Дополнительные сведения об этой структуры, в том числе список его элементов. в разделе **PROPSHEETPAGE** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>CPropertyPage::OnApply  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку ОК или кнопка "Применить".  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эти изменения принимаются; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Когда платформа вызывает эту функцию, принимаются изменения, внесенные на всех страницах свойств в окне свойств, окно свойств сохраняется фокусировки, а `OnApply` возвращает **TRUE** (значение 1). Перед `OnApply` может быть вызван платформой, был вызван [SetModified](#setmodified) и задайте для его параметра **TRUE**. Как только пользователь вносит изменения на странице свойств, активируется кнопка "Применить".  
  
 Переопределите эту функцию-член для указания берет программы, когда пользователь нажимает кнопку Применить. При переопределении метода, функция должна возвращать **TRUE** для принятия изменений и **FALSE** для предотвращения изменения вступают в силу.  
  
 Реализация по умолчанию `OnApply` вызовов `OnOK`.  
  
 Дополнительные сведения о сообщениях уведомлений, отправленных при нажатии применить сейчас или кнопку "ОК" в окне свойств см. в разделе [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertyPage::OnOK](#onok).  
  
##  <a name="oncancel"></a>CPropertyPage::OnCancel  
 Эта функция-член вызывается платформой, когда нажата кнопка "Отмена".  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения действий, кнопку "Отмена". Значение по умолчанию отменяет все изменения, которые были сделаны.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>CPropertyPage::OnKillActive  
 Эта функция-член вызывается платформой, когда страница больше не является активной.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные были обновлены успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач проверки специальных данных.  
  
 Реализация по умолчанию эта функция-член копирует параметры из элементов управления на странице свойств для переменных-членов страницы свойств. Если данные не были успешно обновлены из-за ошибки при проверке (DDV) данных диалогового окна, страницы сохраняет фокус.  
  
 После этого функция-член возвращает успешно, платформа вызывает страницы [OnOK](#onok) функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>CPropertyPage::OnOK  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку ОК или кнопка "Применить", сразу после платформа вызывает [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь нажимает OK или кнопка "Применить", платформа получает [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) уведомления на странице свойств. Вызов `OnOK` не будет выполняться при вызове метода [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) так, как страницы свойств в этом случае не отправлять уведомления.  
  
 Переопределите эту функцию-член для реализации дополнительное поведение, характерное для текущей активной страницы, когда пользователь закрывает окно свойств целиком.  
  
 Реализация по умолчанию эта функция-член помечает страницу как «очистить», чтобы отразить, что данные были обновлены в `OnKillActive` функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView 116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>CPropertyPage::OnQueryCancel  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Отмена" и до отмены было выполнено действие.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **FALSE** для предотвращения операции отмены или значение TRUE, чтобы разрешить его.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для задания действия, программа может потребоваться при нажатии кнопки "Отмена".  
  
 Реализация по умолчанию `OnQueryCancel` возвращает **TRUE**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>CPropertyPage::OnReset  
 Эта функция-член вызывается платформой, когда пользователь нажимает кнопку "Отмена".  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Примечания  
 Когда платформа вызывает эту функцию, отменяются изменения, внесенные на все страницы свойств, внесенные пользователем, ранее кнопку "Применить", и окно свойств сохраняет фокус.  
  
 Переопределите эту функцию-член для указания программа принимает, когда пользователь нажимает кнопку "Отмена".  
  
 Реализация по умолчанию `OnReset` не выполняет никаких действий.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="onsetactive"></a>CPropertyPage::OnSetActive  
 Эта функция-член вызывается платформой, когда страница выбранного пользователем и станет активной.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если страницы был успешно задан активно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач при активации страницы. Переопределенный эта функция-член обычно вызывается версия по умолчанию после обновления элементов данных, чтобы его можно обновить элементы управления страницы новыми данными.  
  
 Реализация по умолчанию создает окно страницы, если не создан ранее и делает активной странице.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="onwizardback"></a>CPropertyPage::OnWizardBack  
 Эта функция-член вызывается платформой, когда пользователь щелкает кнопка "Назад" в мастере.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, чтобы автоматически перейти на следующую страницу; значение -1, чтобы предотвратить изменение страницы. Чтобы перейти на страницу, отличном от того, далее, возвращайте идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для указания какие-либо действия, который должен выполнить пользователь при нажатии кнопки «Назад».  
  
 Дополнительные сведения о том, как сделать листа свойств мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>CPropertyPage::OnWizardFinish  
 Эта функция-член вызывается платформой, когда пользователь щелкает на "Готово", с помощью мастера.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств уничтожается после завершения работы мастера; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает **Готово** кнопку в мастере, платформа вызывает эту функцию; когда `OnWizardFinish` возвращает **TRUE** (ненулевое значение), окно свойств может уничтожить (но не удаляется). Вызовите `DestroyWindow` уничтожить окно свойств. Не вызывайте `DestroyWindow` из `OnWizardFinish`; это будет привести к повреждение кучи или другие ошибки.  
  
 Можно переопределить эту функцию-член для указания какие-либо действия, который должен выполнить пользователь при нажатии кнопки "Готово". При переопределении этого функции возвращают **FALSE** для предотвращения удаления страницы свойств.  
  
 Дополнительные сведения о сообщениях уведомлений, отправленных при нажатии кнопки «Готово» в окне свойств мастера см. в разделе [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о том, как сделать листа свойств мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>CPropertyPage::OnWizardNext  
 Эта функция-член вызывается платформой при нажатии кнопки "Далее", с помощью мастера.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, чтобы автоматически перейти на следующую страницу; значение -1, чтобы предотвратить изменение страницы. Чтобы перейти на страницу, отличном от того, далее, возвращайте идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для указания какие-либо действия, который должен выполнить пользователь при нажатии кнопки следующий.  
  
 Дополнительные сведения о том, как сделать листа свойств мастера см. в разделе [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>CPropertyPage::QuerySiblings  
 Вызовите эту функцию-член для пересылки сообщения для каждой страницы в окне свойств.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `wParam`  
 Указывает Дополнительные сведения, зависящие от сообщения.  
  
 `lParam`  
 Указывает Дополнительные сведения, зависящие от сообщения  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение со страницы в окне свойств, или 0, если все страницы возвращают значение 0.  
  
### <a name="remarks"></a>Примечания  
 Если страница возвращает ненулевое значение, окно свойств не отправляет сообщения на последующих страницах.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>CPropertyPage::SetModified  
 Вызовите эту функцию-член для включения или отключения кнопка "Применить", зависимости от того, следует ли применять параметры на странице свойств для соответствующего внешнего объекта.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bChanged`  
 **Значение TRUE,** для указания, что параметры страницы свойств были изменены с момента последнего они были применены; **FALSE** для указания, что были применены параметры страницы свойств, или следует игнорировать.  
  
### <a name="remarks"></a>Примечания  
 Платформа поддерживает отслеживания, из которых страниц «грязных», то есть, страницы свойств, для которых был вызван **SetModified (TRUE)**. Кнопка "Применить" всегда включен при вызове метода **SetModified (TRUE)** для одной из страниц. Кнопка "Применить" будет отключена при вызове **SetModified (FALSE)** для одной из страниц, но только если ни один из других страниц является «грязным».  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView #127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [Образец CMNCTRL2 MFC](../../visual-cpp-samples.md)   
 [Пример MFC PROPDLG](../../visual-cpp-samples.md)   
 [Пример MFC: SNAPVW](../../visual-cpp-samples.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPropertySheet-класс](../../mfc/reference/cpropertysheet-class.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)

