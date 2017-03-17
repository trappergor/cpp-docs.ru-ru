---
title: "Класс CSnapInPropertyPageImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f5db4d0742a423e9574db2a4268a9376491b2ed2
ms.lasthandoff: 02/24/2017

---
# <a name="csnapinpropertypageimpl-class"></a>Класс CSnapInPropertyPageImpl
Этот класс предоставляет методы для реализации объекта страницы свойств оснастки.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Изменяет состояние **ОК** и **отменить** кнопки.|  
|[CSnapInPropertyPageImpl::Create](#create)|Инициализирует только что созданный `CSnapInPropertyPageImpl` объекта.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Вызывается платформой, когда пользователь щелкает **Apply Now** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Вызывается платформой, когда пользователь щелкает **помочь** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Вызывается платформой, когда текущая страница больше не активна.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Вызывается платформой, когда пользователь щелкает **отменить** кнопки и до отмены.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Вызывается платформой, когда пользователь щелкает **Сброс** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Вызывается платформой, когда текущая страница становится активным.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Вызывается платформой, когда пользователь щелкает **обратно** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Вызывается платформой, когда пользователь щелкает **Готово** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Вызывается платформой, когда пользователь щелкает `Next` кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Пересылает текущее сообщение для всех страниц свойств.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Вызов, чтобы активировать или деактивировать **Apply Now** кнопки.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE** структура, используемая `CSnapInPropertyPageImpl` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CSnapInPropertyPageImpl`Предоставляет базовую реализацию для объекта страницы свойств оснастки. Основные возможности страницы свойств оснастки реализуются с помощью нескольких различных интерфейсов и сопоставления типов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsnap.h  
  
##  <a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 Эта функция вызывается после неустранимой изменений данных на странице модальную страницу свойств.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция будет изменить **ОК** кнопки **закрыть** и отключить **отменить** кнопки. Это изменение оповещения, что изменение является постоянным и изменения пользователя не может быть отменено.  
  
 `CancelToClose` Функция-член не выполняет никаких действий в немодальное свойств, поскольку немодальный лист свойств не имеет **отменить** кнопки по умолчанию.  
  
##  <a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Создает объект `CSnapInPropertyPageImpl`.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTitle`  
 [in] Заголовок страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Чтобы инициализировать базовой структуры, вызовите [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="create"></a>CSnapInPropertyPageImpl::Create  
 Эта функция вызывается для инициализации основную структуру страницы свойств.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор **PROPSHEETPAGE** структуру, содержащую атрибуты вновь созданный свойств.  
  
### <a name="remarks"></a>Примечания  
 Сначала следует вызвать [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) перед вызовом этой функции.  
  
##  <a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`представляет собой структуру, члены которого хранения характеристики **PROPSHEETPAGE**.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Примечания  
 Используйте эту структуру для инициализации внешний вид страницы свойств после его создания.  
  
 Дополнительные сведения об этой структуры, включая список ее членов в разделе [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 Эта функция-член вызывается, когда пользователь щелкает **ОК** или **Apply Now** кнопки.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эти изменения принимаются; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Перед `OnApply` может быть вызван платформой, то необходимо вызвать метод `SetModified` и задайте параметра **TRUE**. Это активирует **Apply Now** кнопку по мере внесения изменений на странице свойств.  
  
 Переопределение для указания принимает программы, когда пользователь нажимает эту функцию-член **Apply Now** кнопки. При переопределении метода, функция должна возвращать **TRUE** для принятия изменений и **FALSE** для предотвращения изменения вступают в силу.  
  
 Реализация по умолчанию `OnApply` возвращает **TRUE**.  
  
##  <a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 Эта функция-член вызывается, когда пользователь щелкает **помочь** кнопку на странице свойств.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для отображения справки для страницы свойств.  
  
##  <a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 Эта функция-член вызывается в том случае, если страница больше не является активной страницы.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данных был успешно обновлен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач проверки специальных данных.  
  
##  <a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 Эта функция-член вызывается, когда пользователь щелкает **отменить** кнопку и до отмены было выполнено действие.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, чтобы разрешить операции отмены; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания программа принимает, когда пользователь щелкает действие **отменить** кнопки.  
  
 Реализация по умолчанию `OnQueryCancel` возвращает **TRUE**.  
  
##  <a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 Эта функция-член вызывается, когда пользователь щелкает **отменить** кнопки.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции изменяется на все страницы свойств, сделанные ранее щелчок **Apply Now** кнопки, удаляются, и окно свойств сохраняет фокус.  
  
 Переопределить эту функцию-член для указания программа принимает, когда пользователь щелкает **отменить** кнопки.  
  
##  <a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 Эта функция-член вызывается при выбранной пользователем страницы и становится активной страницей.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если страницы был успешно установлен активно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач, когда страница активируется. Переопределение функции-члена следует вызвать версию по умолчанию, перед выполнением какой-либо другой обработки.  
  
 Реализация по умолчанию возвращает **TRUE**.  
  
##  <a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 Эта функция-член вызывается, когда пользователь щелкает **обратно** кнопку в мастере.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
-   0, чтобы автоматически перейти к предыдущей странице.  
  
-   значение -1, чтобы предотвратить изменение страницы.  
  
 Для перехода на страницу, не является следующим возвращают идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания некоторые действия должен выполнить пользователь при **обратно** кнопки.  
  
##  <a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 Эта функция-член вызывается, когда пользователь щелкает **Готово** кнопку в мастере.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств уничтожается после завершения работы мастера; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания некоторые действия должен выполнить пользователь при **Готово** кнопки.  
  
##  <a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 Эта функция-член вызывается, когда пользователь щелкает `Next` кнопку в мастере.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
-   0, чтобы автоматически перейти на следующую страницу.  
  
-   значение -1, чтобы предотвратить изменение страницы.  
  
 Для перехода на страницу, не является следующим возвращают идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания некоторые действия должен выполнить пользователь при `Next` нажатии кнопки.  
  
##  <a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
 Вызовите эту функцию-член для пересылки сообщения на каждую страницу в окне свойств.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `wParam`  
 [in] Задает дополнительные сведения, зависящие от сообщения.  
  
 `lParam`  
 [in] Задает дополнительные сведения, зависящие от сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение не будут перенаправляться на следующую страницу свойств; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Если страница возвращает ненулевое значение, окно свойств не отправляет сообщение последующих страниц.  
  
##  <a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 Вызовите эту функцию-член для включения или отключения **Apply Now** кнопки в зависимости от того, следует ли применять параметры на странице свойств для соответствующего внешнего объекта.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bChanged`  
 [in] **TRUE** для указания, что параметры страницы свойств были изменены со времени последнего, они были применены; **FALSE** были применены параметры страницы свойств или игнорироваться.  
  
### <a name="remarks"></a>Примечания  
 Окно свойств отслеживает отслеживания, из которых страницы «грязных», то есть, страницы свойств, для которых был вызван **SetModified (TRUE)**. **Apply Now** кнопка будет всегда включена, при вызове **SetModified (TRUE)** для одной из страниц. **Apply Now** кнопка будет отключена при вызове **SetModified (FALSE)** для одной из страниц, но только если ни один из других страниц «грязным».  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

