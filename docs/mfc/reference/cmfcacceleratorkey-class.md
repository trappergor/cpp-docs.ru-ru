---
title: "Класс CMFCAcceleratorKey | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey class
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
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
ms.openlocfilehash: 7baa210acfabe8f17e2ab747fd98fe463c2907a2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkey-class"></a>Класс CMFCAcceleratorKey
Вспомогательный класс, реализующий виртуальное ключевое сопоставление и форматирование.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Создает объект `CMFCAcceleratorKey`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|Преобразует структуры УСКОРЕНИЕ, визуальное представление.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Задает сочетание клавиш для `CMFCAcceleratorKey` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Сочетания клавиш, называются сочетания клавиш. Если вы хотите отобразить сочетания клавиш, вводимые пользователем, [CMFCAcceleratorKeyAssignCtrl класс](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) сопоставляет сочетания клавиш, например Alt + Shift + S пользовательский текстовый формат, например «Alt + Shift + S». Каждый `CMFCAcceleratorKey` объект сопоставляется одному сочетанию клавиш в текстовом формате.  
  
 Дополнительные сведения об использовании сочетаний клавиш и таблицы сочетаний клавиш см. в разделе [CKeyboardManager класса](../../mfc/reference/ckeyboardmanager-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCAcceleratorKey` объекта и как использовать его `Format` метод.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#30;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 Создает [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) объекта.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpAccel`  
 Указатель на сочетание клавиш.  
  
### <a name="remarks"></a>Примечания  
 Если при создании не предоставляют сочетания клавиш `CMFCAccleratorKey`, используйте [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) метод, чтобы связать сочетания клавиш с вашей `CMFCAcceleratorKey` объекта.  
  
##  <a name="format"></a>CMFCAcceleratorKey::Format  
 Преобразует структуру УСКОРЕНИЕ связанные строковому значению.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `str`  
 Ссылку на `CString` объекта, где метод записывает переведенные сочетания клавиш.  
  
### <a name="remarks"></a>Примечания  
 Этот метод извлекает строку формата сочетанием клавиш. Можно задать формат строки [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) объекта с помощью конструктора или метода [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).  
  
##  <a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 Задает сочетание клавиш для [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) объекта.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpAccel`  
 Указатель на сочетание клавиш.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать сочетание клавиш для `CMFCAcceleratorKey` Если вы не указали сочетания клавиш при создании `CMFCAcceleratorKey`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

