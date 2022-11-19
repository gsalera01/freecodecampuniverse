# freecodecampuniverse
--
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

--
-- Name: galaxy; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.galaxy (
    color text NOT NULL,
    distance_milkyway integer NOT NULL,
    number_of_stars numeric,
    distance integer,
    has_life boolean,
    name character varying(100),
    galaxy_id integer NOT NULL
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    color text NOT NULL,
    phase integer NOT NULL,
    astronaut_visits integer,
    full_moon boolean,
    craters integer,
    degrees integer,
    goddess text,
    distance integer,
    name character varying(100),
    moon_id integer NOT NULL
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    color text NOT NULL,
    order_from_sun text,
    rings integer,
    has_life boolean NOT NULL,
    is_gas boolean,
    distance integer,
    name character varying(100),
    planet_id integer NOT NULL
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_star_id_seq OWNER TO freecodecamp;

--
-- Name: planet_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_star_id_seq OWNED BY public.planet.planet_id;


--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    color text NOT NULL,
    sign text NOT NULL,
    links integer,
    distance integer,
    has_life boolean,
    name character varying(100),
    star_id integer NOT NULL
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: sun; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.sun (
    color text NOT NULL,
    flares integer NOT NULL,
    rays integer,
    has_life boolean,
    distance integer,
    name character varying(100),
    sun_id integer NOT NULL
);


ALTER TABLE public.sun OWNER TO freecodecamp;

--
-- Name: sun_sun_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.sun_sun_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.sun_sun_id_seq OWNER TO freecodecamp;

--
-- Name: sun_sun_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.sun_sun_id_seq OWNED BY public.sun.sun_id;


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_star_id_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Name: sun sun_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.sun ALTER COLUMN sun_id SET DEFAULT nextval('public.sun_sun_id_seq'::regclass);


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES ('green', 456, 26, NULL, NULL, NULL, 1);
INSERT INTO public.galaxy VALUES ('red', 789, 37, NULL, NULL, NULL, 2);
INSERT INTO public.galaxy VALUES ('purple', 67, 456, NULL, NULL, NULL, 3);
INSERT INTO public.galaxy VALUES ('yellow', 567, 234, NULL, NULL, NULL, 4);
INSERT INTO public.galaxy VALUES ('pink', 29, 2087, NULL, NULL, NULL, 5);
INSERT INTO public.galaxy VALUES ('blue', 123, 15, NULL, NULL, NULL, 6);


--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES ('blue', 1, 5, NULL, NULL, 1, NULL, NULL, NULL, 1);
INSERT INTO public.moon VALUES ('green', 2, 8, NULL, NULL, 1, NULL, NULL, NULL, 2);
INSERT INTO public.moon VALUES ('red', 5, 10, NULL, NULL, 1, NULL, NULL, NULL, 3);
INSERT INTO public.moon VALUES ('purple', 4, NULL, NULL, NULL, 1, NULL, 1, NULL, 4);
INSERT INTO public.moon VALUES ('yellow', 3, NULL, NULL, NULL, 1, NULL, 2, NULL, 5);
INSERT INTO public.moon VALUES ('pink', 6, NULL, NULL, NULL, 2, NULL, 3, NULL, 6);
INSERT INTO public.moon VALUES ('brown', 7, NULL, NULL, NULL, 11, NULL, 4, NULL, 7);
INSERT INTO public.moon VALUES ('gold', 8, NULL, NULL, NULL, 12, NULL, 5, NULL, 8);
INSERT INTO public.moon VALUES ('orange', 9, NULL, NULL, NULL, 13, NULL, 6, NULL, 9);
INSERT INTO public.moon VALUES ('grey', 10, NULL, NULL, NULL, 14, NULL, 7, NULL, 10);
INSERT INTO public.moon VALUES ('black', 11, NULL, NULL, NULL, 15, NULL, 8, NULL, 11);
INSERT INTO public.moon VALUES ('white', 12, NULL, NULL, NULL, 16, NULL, 9, NULL, 12);
INSERT INTO public.moon VALUES ('silver', 13, NULL, NULL, NULL, 17, NULL, 10, NULL, 13);
INSERT INTO public.moon VALUES ('peach', 14, NULL, NULL, NULL, 18, NULL, 11, NULL, 14);
INSERT INTO public.moon VALUES ('ruby', 15, NULL, NULL, NULL, 19, NULL, 12, NULL, 15);
INSERT INTO public.moon VALUES ('olive', 16, NULL, NULL, NULL, 20, NULL, 13, NULL, 16);
INSERT INTO public.moon VALUES ('violet', 17, NULL, NULL, NULL, 21, NULL, 14, NULL, 17);
INSERT INTO public.moon VALUES ('fawn', 18, NULL, NULL, NULL, 22, NULL, 15, NULL, 18);
INSERT INTO public.moon VALUES ('lilac', 19, NULL, NULL, NULL, 23, NULL, 16, NULL, 19);
INSERT INTO public.moon VALUES ('cream', 20, NULL, NULL, NULL, 24, NULL, 17, NULL, 20);


--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES ('purple', NULL, NULL, true, NULL, NULL, NULL, 1);
INSERT INTO public.planet VALUES ('yellow', NULL, NULL, false, NULL, NULL, NULL, 2);
INSERT INTO public.planet VALUES ('pink', NULL, NULL, true, NULL, NULL, NULL, 3);
INSERT INTO public.planet VALUES ('orange', NULL, NULL, false, NULL, NULL, NULL, 4);
INSERT INTO public.planet VALUES ('grey', NULL, NULL, true, NULL, NULL, NULL, 5);
INSERT INTO public.planet VALUES ('white', NULL, NULL, false, NULL, NULL, NULL, 6);
INSERT INTO public.planet VALUES ('black', NULL, NULL, true, NULL, NULL, NULL, 7);
INSERT INTO public.planet VALUES ('brown', NULL, NULL, false, NULL, NULL, NULL, 8);
INSERT INTO public.planet VALUES ('cream', NULL, NULL, true, NULL, NULL, NULL, 9);
INSERT INTO public.planet VALUES ('gold', NULL, NULL, false, NULL, NULL, NULL, 10);
INSERT INTO public.planet VALUES ('blue', NULL, NULL, true, NULL, 1, NULL, 11);
INSERT INTO public.planet VALUES ('green', NULL, NULL, false, NULL, 2, NULL, 12);


--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES ('blue', '1', 1, NULL, NULL, NULL, 1);
INSERT INTO public.star VALUES ('green', '2', 2, NULL, NULL, NULL, 2);
INSERT INTO public.star VALUES ('red', '3', 3, NULL, NULL, NULL, 3);
INSERT INTO public.star VALUES ('purple', '4', 4, NULL, NULL, NULL, 4);
INSERT INTO public.star VALUES ('yellow', '5', 5, NULL, NULL, NULL, 5);
INSERT INTO public.star VALUES ('pink', '6', 6, NULL, NULL, NULL, 6);


--
-- Data for Name: sun; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.sun VALUES ('blue', 350, 234567, NULL, NULL, NULL, 1);
INSERT INTO public.sun VALUES ('green', 2443, 23153, NULL, NULL, NULL, 2);
INSERT INTO public.sun VALUES ('red', 235, 64422, NULL, NULL, NULL, 3);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 6, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 20, true);


--
-- Name: planet_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_star_id_seq', 12, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 6, true);


--
-- Name: sun_sun_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.sun_sun_id_seq', 3, true);


--
-- Name: galaxy galaxy_distance_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_distance_key UNIQUE (distance);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);


--
-- Name: moon moon_craters_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_craters_key UNIQUE (craters);


--
-- Name: moon moon_distance_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_distance_key UNIQUE (distance);


--
-- Name: moon moon_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_pkey PRIMARY KEY (moon_id);


--
-- Name: planet planet_distance_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_distance_key UNIQUE (distance);


--
-- Name: planet planet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_pkey PRIMARY KEY (planet_id);


--
-- Name: star star_distance_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_distance_key UNIQUE (distance);


--
-- Name: star star_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_pkey PRIMARY KEY (star_id);


--
-- Name: sun sun_distance_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.sun
    ADD CONSTRAINT sun_distance_key UNIQUE (distance);


--
-- Name: sun sun_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.sun
    ADD CONSTRAINT sun_pkey PRIMARY KEY (sun_id);


--
-- Name: star fk_galaxy_id; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT fk_galaxy_id FOREIGN KEY (star_id) REFERENCES public.star(star_id);


--
-- Name: galaxy fk_star_id; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT fk_star_id FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- PostgreSQL database dump complete
--
