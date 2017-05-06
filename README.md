# hello-word


package Bean.gestion;

import otro.ResultadoBean;
import javax.faces.bean.ManagedBean;
import javax.faces.bean.RequestScoped;
import javax.faces.context.FacesContext;

@ManagedBean
@RequestScoped

public class PersonaBean {
    
    private String texto;

    public String getTexto() {
        return texto;
    }

    public void setTexto(String texto) {
        this.texto = texto;
    }
    
  public void transferir(){
    FacesContext context=FacesContext.getCurrentInstance();
    ResultadoBean rb=context.getApplication().evaluateExpressionGet(context, "#{resultadoBean}", ResultadoBean.class);
    rb.setResultado(this.texto);
    }
    
}

