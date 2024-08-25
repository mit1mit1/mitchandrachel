<script setup lang="ts">
	import { browser } from '$app/environment';
	let isAuthenticated: any = 'loading';
	export let hashedPassword: number = 0;
	if (browser) {
		const storedPassword = parseInt(localStorage.getItem('hashedPassword') || '0');
		if (storedPassword) {
			hashedPassword = storedPassword;
		}
	}

	export const cyrb53 = (str: string, seed = 0) => {
		str = str.toLowerCase();
		let h1 = 0xdeadbeef ^ seed,
			h2 = 0x41c6ce57 ^ seed;
		for (let i = 0, ch; i < str.length; i++) {
			ch = str.charCodeAt(i);
			h1 = Math.imul(h1 ^ ch, 2654435761);
			h2 = Math.imul(h2 ^ ch, 1597334677);
		}
		h1 = Math.imul(h1 ^ (h1 >>> 16), 2246822507);
		h1 ^= Math.imul(h2 ^ (h2 >>> 13), 3266489909);
		h2 = Math.imul(h2 ^ (h2 >>> 16), 2246822507);
		h2 ^= Math.imul(h1 ^ (h1 >>> 13), 3266489909);

		return 4294967296 * (2097151 & h2) + (h1 >>> 0);
	};

	$: isAuthenticated = hashedPassword === 7691749211987398 ? 'authenticated' : '';
</script>

<div>
	{#if isAuthenticated === 'loading'}
		...
	{:else if isAuthenticated === 'authenticated'}
		<slot />
	{:else}
		<div class="flexCenter">
			<div class="loginContainer">
				<div class="field">
					<div>Enter Password</div>
					<input
						on:input={(e) => {
							hashedPassword = cyrb53(e?.currentTarget?.value ?? '', 24);
							localStorage.setItem('hashedPassword', hashedPassword.toString());
						}}
					/>
				</div>
			</div>
		</div>
	{/if}
</div>

<style>
	.field {
		display: flex;
		flex-direction: column;
		gap: 5px;
		max-width: 300px;
	}

	.field input {
		padding: 5px;
	}

	.loginContainer {
		display: inline-block;
		min-width: 50%;
		padding: 30px;
		background-color: rgba(240, 240, 240, 0.90);
		border-radius: 10px;
	}

	.flexCenter {
		display: flex;
		justify-content: center;
		margin-top: 50px;
	}
</style>
