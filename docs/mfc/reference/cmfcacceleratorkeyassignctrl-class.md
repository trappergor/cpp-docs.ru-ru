---
title: "Класс CMFCAcceleratorKeyAssignCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl class
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
caps.latest.revision: 33
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
ms.openlocfilehash: 23687cf4c13881293d10a5f816a2c825180df49c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>Класс CMFCAcceleratorKeyAssignCtrl
`CMFCAcceleratorKeyAssignCtrl` Расширяет класс [CEdit Class](../../mfc/reference/cedit-class.md) для поддержки дополнительных системных клавиш, например ALT, CONTROL и SHIFT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Создает объект `CMFCAcceleratorKeyAssignCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Извлекает `ACCEL` структуру для сочетания клавиш, нажатого в объекте `CMFCAcceleratorKeyAssignCtrl`.|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Определяет, задано ли сочетание клавиш.|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для перевода оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Сбрасывает сочетание клавиш.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс расширяет функциональность класса `CEdit` благодаря поддержке сочетаний клавиш. `CMFCAcceleratorKeyAssignCtrl` Функции как класса [CEdit Class](../../mfc/reference/cedit-class.md) и также может распознавать системные кнопки.  
  
 Этот класс сопоставляет физические сочетания клавиш со строковыми значениями. Например, пусть сочетание клавиш ALT+B сопоставлено со строкой "Alt + B". Когда пользователь нажимает это сочетание клавиш в объекте `CMFCAcceleratorKeyAssignCtrl`, отображается строка "Alt + B". Дополнительные сведения о сопоставлении между сочетания клавиш и формат строки см. в разделе [CMFCAcceleratorKey класса](../../mfc/reference/cmfcacceleratorkey-class.md).  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта `CMFCAcceleratorKeyAssignCtrl` и использование его метода `ResetKey` для сброса сочетания клавиш.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#31;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CMFCAcceleratorKeyAssignCtrl`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxacceleratorkeyassignctrl.h  
  
##  <a name="a-namecmfcacceleratorkeyassignctrla--cmfcacceleratorkeyassignctrlcmfcacceleratorkeyassignctrl"></a><a name="cmfcacceleratorkeyassignctrl"></a>CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl  
 Создает [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) объекта.  
  
```  
CMFCAcceleratorKeyAssignCtrl();
```  
  
##  <a name="a-namegetaccela--cmfcacceleratorkeyassignctrlgetaccel"></a><a name="getaccel"></a>CMFCAcceleratorKeyAssignCtrl::GetAccel  
 Извлекает `ACCEL` структуры для нажатия сочетания клавиш в [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) объекта.  
  
```  
ACCEL const* GetAccel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `ACCEL` Структура, описывающая сочетание клавиш.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию для получения `ACCEL` структуры для сочетания клавиш, введенные пользователем в вашей `CMFCAcceleratorKeyAssignCtrl` объекта.  
  
##  <a name="a-nameisfocuseda--cmfcacceleratorkeyassignctrlisfocused"></a><a name="isfocused"></a>CMFCAcceleratorKeyAssignCtrl::IsFocused  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsFocused() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameiskeydefineda--cmfcacceleratorkeyassignctrliskeydefined"></a><a name="iskeydefined"></a>CMFCAcceleratorKeyAssignCtrl::IsKeyDefined  
 Определяет, было ли определено сочетания клавиш в [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) объекта.  
  
```  
BOOL IsKeyDefined() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь нажал уже допустимые сочетания клавиш, определяющие сочетания клавиш; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет определить, является ли пользователь ввел допустимое сочетание клавиш в вашей `CMFCAcceleratorKeyAssignCtrl` объекта. Если существует сочетание клавиш, можно использовать [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) метод, чтобы получить `ACCEL` структура, связанная с этого сочетания клавиш.  
  
##  <a name="a-namepretranslatemessagea--cmfcacceleratorkeyassignctrlpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameresetkeya--cmfcacceleratorkeyassignctrlresetkey"></a><a name="resetkey"></a>CMFCAcceleratorKeyAssignCtrl::ResetKey  
 Сбрасывает сочетание клавиш.  
  
```  
void ResetKey();
```  
  
### <a name="remarks"></a>Примечания  
 Функция очищает изменить текст элемента управления. Сюда входят все сочетания клавиш, нажата.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)

