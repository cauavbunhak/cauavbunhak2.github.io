document.addEventListener("DOMContentLoaded", function () {

    // Anúncios do carrossel //
    var listaDeBanners = [
        {
            titulo: "Arranhadores para gatos",
            desc: "Arranhador pequeno com descanso para garantir o bem-estar do seu felino por R$ 37,00.",
            img: "imagens/arranhador.png",
            alt: "Foto do arranhador pequeno para gatos com descanso superior"
        },
        {
            titulo: "Corda de escalada para gatos",
            desc: "Corda suspensa com fixação de teto para diversão do pet por R$ 55,00.",
            img: "imagens/corda gatos.png",
            alt: "Foto da corda suspensa para gatos"
        }
    ];

    var posicaoAtual = 0;
    var campoTitulo = document.getElementById("titulo-banner");
    var campoDesc = document.getElementById("desc-banner");
    var campoImg = document.getElementById("img-banner");

    function trocarAnuncio() {
        if (campoTitulo && campoDesc && campoImg) {
            campoTitulo.innerText = listaDeBanners[posicaoAtual].titulo;
            campoDesc.innerText = listaDeBanners[posicaoAtual].desc;
            campoImg.src = listaDeBanners[posicaoAtual].img;
            campoImg.alt = listaDeBanners[posicaoAtual].alt;
            
            posicaoAtual = (posicaoAtual + 1) % listaDeBanners.length;
        }
    }

    // Inicializa e define o tempo de 4 segundos //
    trocarAnuncio();
    setInterval(trocarAnuncio, 4000);


    var inputCpf = document.getElementById("cpf");
    if (inputCpf) {
        inputCpf.addEventListener("blur", function () {
            var textoCpfLimpo = inputCpf.value.replace(/[.-]+/g, "");
            console.log("CPF processado internamente: " + textoCpfLimpo);
        });
    }


    // Validação do formulário no botão //
    var formAgendar = document.getElementById("formAgendamento");
    if (formAgendar) {
        formAgendar.addEventListener("submit", function (evento) {
            
            // Validação de campos obrigatórios //
            if (!formAgendar.checkValidity()) {
                alert("Por favor, preencha todos os campos obrigatórios marcados com *.");
                evento.preventDefault();
                return;
            }

            var banhoChecado = document.getElementById("srvBanho").checked;
            var vacinaChecada = document.getElementById("srvVacina").checked;

            if (!banhoChecado && !vacinaChecada) {
                alert("Selecione pelo menos um serviço (Higiene ou Saúde) para fechar o agendamento.");
                evento.preventDefault();
                return;
            }

            var opcaoLogistica = document.getElementById("logistica").value;
            if (banhoChecado && !vacinaChecada && opcaoLogistica === "telebusca") {
                alert("O serviço de Corte de unhas, banho e tosa está disponível apenas para atendimento no local do estabelecimento. Por favor, altere a forma de atendimento.");
                evento.preventDefault();
                return;
            }

            alert("Agendamento processado com sucesso!");
        });
    }
});
