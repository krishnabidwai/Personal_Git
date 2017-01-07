({
	navigateToRecord : function(component, event, helper) {
        var device = $A.get("$Browser.formFactor");
        if(device != 'DESKTOP')
        {
            var navEvent = $A.get("e.force:navigateToSObject");
            navEvent.setParams({
                recordId: component.get("v.objSobject").Id,
                slideDevName: "detail"
            });
            navEvent.fire(); 
        }
        else
        {
            window.location='/'+component.get("v.objSobject").Id+'';
        }
	}
})