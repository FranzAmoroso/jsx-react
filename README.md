# JSX

JSX, acronimo di JavaScript XML, è una sintassi di estensione di JavaScript che consente di scrivere in modo dichiarativo e simile all'HTML all'interno di codice JavaScript. È ampiamente utilizzato in React per descrivere la struttura dell'interfaccia utente (UI) in modo più intuitivo.

##### Sintassi Familiare a HTML:

JSX assomiglia a HTML, semplificando la scrittura di struttura UI all'interno del codice JavaScript.

    const element = <h1>Hello, JSX!</h1>;

##### Espressioni JavaScript:

Puoi incorporare espressioni JavaScript all'interno di JSX utilizzando le parentesi graffe {}.

    const name = "React";
    const element = <h1>Hello, {name}!</h1>;

##### Elementi JSX:

Gli elementi JSX sono simili agli elementi HTML e possono avere attributi e figli.

    const element = (
        <div className="container">
            <p>Contenuto JSX</p>
        </div>
    );

##### Attributi dinamici:

Puoi utilizzare variabili o espressioni JavaScript per impostare dinamicamente gli attributi JSX.

    const color = "blue";
    const element = <div style={{ color: color }}>Testo colorato</div>;

##### Componenti React:

JSX può essere utilizzato per definire componenti React, sia funzionali che basati su classi.

    function MyComponent() {
        return <p>Sono un componente React!</p>;
    }

##### Evento e Gestori:

Gli eventi possono essere gestiti in JSX utilizzando la sintassi di gestione degli eventi React.

    function handleClick() {
        alert("Cliccato!");
    }
    const button = <button onClick={handleClick}>Clicca qui</button>;

#### Risparmio di Righe:

JSX semplifica la creazione di struttura complessa, riducendo la necessità di concatenare stringhe o utilizzare chiamate di funzioni per creare elementi.

    const complexElement = (
        <div>
            <h2>Titolo</h2>
            <ul>
            <li>Elemento 1</li>
            <li>Elemento 2</li>
            </ul>
        </div>
    );

##### Inclusione Condizionale:

JSX può essere utilizzato all'interno delle espressioni condizionali per rendere dinamica la struttura.

        const isLoggedIn = true;

        const element = (
        <div>
            {isLoggedIn ? <p>Utente loggato</p> : <p>Utente non loggato</p>}
        </div>
        );

In sintesi, JSX semplifica la creazione e la gestione della struttura dell'interfaccia utente in React, rendendo il codice più leggibile e simile a HTML. Quando il codice JSX viene compilato, viene tradotto in chiamate di funzioni React per creare gli elementi DOM corrispondenti.

## Return

In React, quando il blocco di codice all'interno di una funzione ha più di una riga di codice nel return, è necessario avvolgere il contenuto tra parentesi tonde.

    function App(){
        return (
            <div>
                <p>Righe</p>
            </div>

        )
    }

Se il return contiene solo una riga di codice, non sono necessarie parentesi.

    function App(){
        return <p>Riga</p>
    }
### rendering
la funzione di rendering (solitamente render o return all'interno di un componente) deve restituire un singolo elemento o un frammento. Un frammento è una sintassi che ti permette di raggruppare più elementi senza aggiungere un elemento aggiuntivo al DOM e al browser viene versato solo il codice al suo interno.
##### Utilizzo di un singolo 
    function ComponenteUno() {
        return (
            <div>
                <p>Contenuto 1</p>
            </div>
        );
    }

##### Utilizzo di un frammento:
I frammenti (indicati con <> e </>) ti consentono di raggruppare più elementi senza aggiungere un nodo DOM aggiuntivo.

    function ComponenteDue() {
        return (
            <>
                <p>Contenuto 2.1</p>
                <p>Contenuto 2.2</p>
            </>
        );
    }
##### Utilizzo di un frammento con chiave:
Aggiungere una chiave (key) a ciascun elemento all'interno di un frammento quando stai mappando un array.

    function ComponenteTre() {
        const items = ["Elemento 3.1", "Elemento 3.2"];

        return (
            <>
                {items.map((item, index) => (
                    <p key={index}>{item}</p>
                ))}
            </>
        );
    }
##### parentesi graffe
Le prime parentesi graffe `{`{}`}` indicano l'inizio di un blocco di codice JavaScript all'interno di JSX, Questo consente di incorporare dinamicamente espressioni JavaScript all'interno del markup JSX. Le seconde parentesi graffe {`{}`} indicano un oggetto JavaScript all'interno del blocco di codice. 

    <img style={{ height:"200px" }} src={/${img}.svg} alt="" />
In questo caso specifico, stiamo definendo un oggetto stile per l'attributo style dell'elemento `<img>`. Questo oggetto ha una singola proprietà, height, che viene impostata su "200px". Quindi utilizza le parentesi graffe in entrambi i modi: per incorporare codice JavaScript e per definire un oggetto JavaScript all'interno di JSX.
