function criaCalculadora() {
  return { // RETURN CRIANDO UM OBJETO
    display: document.querySelector('.display'), // Define o display como um atributo

    inicia() {    // Cria uma função de inicialização que starta outras funções 
      this.cliqueBotoes();
      this.pressionaBackSpace(); // This está se referindo a cria calculadora 
      this.pressionaEnter();
    },

    pressionaBackSpace() { // Para deletar
      this.display.addEventListener('keydown', e => { // Arrow function para o this se manter no escopo da calculadora 
        if (e.keyCode === 8) { // 8 código do backspace
          e.preventDefault(); //??
          this.clearDisplay();
        }
      });
    },

    pressionaEnter() {
      this.display.addEventListener('keyup', e => {
        if (e.keyCode === 13) {
          this.realizaConta();
        }
      });
    },

    realizaConta() {
      let conta = this.display.value; // Captura o valor do display

      try {
        conta = eval(conta); // Eval é a função que realiza contas porém, ela é perigosa pois é acessável

        if(!conta) {
          alert('Conta inválida');
          return;
        }

        this.display.value = String(conta); // Isso é o else 
      } catch(e) {
        alert('Conta inválida');
        return; // Return para parar a execução 
      }
    },

    clearDisplay() {
      this.display.value = '';
    },

    apagaUm() {
      this.display.value = this.display.value.slice(0, -1);
    },


    cliqueBotoes() {
      document.addEventListener('click', e => {
        const el = e.target;

        if(el.classList.contains('btn-num')) {
          this.btnParaDisplay(el.innerText); // Insere no innerText o valor p/ o display com o método criado 
        }

        if(el.classList.contains('btn-clear')) {
          this.clearDisplay();
        }

        if(el.classList.contains('btn-del')) {
          this.apagaUm();
        }

        if(el.classList.contains('btn-eq')) {
          this.realizaConta();
        }

        this.display.focus();
      });
    },

    btnParaDisplay(valor) {
      this.display.value += valor; // Inserir o valor no display
    }

  };
}

const calculadora = criaCalculadora(); // Atribui toda a função construtora a constante
calculadora.inicia();// Executa a função com o método criado 
